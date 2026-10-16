# Model Card: GraphSAGE SSTA Forecaster (Tutorial Model)

Following Mitchell et al. (2019), *Model Cards for Model Reporting* ([arXiv:1810.03993](https://arxiv.org/abs/1810.03993)).

## Model Details

- **Developed by:** the tutorial authors (names withheld for anonymous review), as the worked example of the tutorial *Graph Neural Networks for Ocean Forecasting: Predicting Sea Surface Temperature Anomalies and Marine Heatwave Precursors* (Climate Change AI workshop, NeurIPS 2026).
- **Model date:** October 2026.
- **Model type:** Graph neural network — a two-layer GraphSAGE (Hamilton et al., 2017; mean aggregation, hidden width 128, ReLU, dropout 0.2) with a linear head, implemented in PyTorch Geometric. Approximately 36,000 trainable parameters (~149 kB checkpoint).
- **Input:** for each of 4,349 ocean nodes, the 12 most recent months of sea surface temperature anomaly (SSTA) at that node. Spatial structure enters exclusively through the graph: a hybrid correlation graph (68,786 directed edges; ≈16 per node) combining each node's most-correlated partners with dedicated long-range "teleconnection" edges beyond ~3,300 km.
- **Output:** the SSTA at every node one month ahead; longer leads are produced recursively.
- **Training objective:** mean squared error; Adam (lr 10⁻³, weight decay 10⁻⁵), 30 epochs with validation-based model selection. Training takes ~1 minute on a free Colab T4 GPU.
- **Simplified re-implementation** of the approach of Ning et al. (2024), *Earth and Space Science*, 11, e2023EA003455, https://doi.org/10.1029/2023EA003455. The published study's own model, checkpoints, and graph tool are archived at DOIs 10.5281/zenodo.10702459, .10702592, .10702598.
- **License:** MIT. **Questions or feedback:** via the issue tracker of the tutorial's accompanying repository (identifying details withheld during review).

## Intended Use

- **Primary intended use:** pedagogy. The model exists to demonstrate, within a tutorial notebook, how a gridded ocean dataset is converted into a graph, how a GNN is trained on it, and how such forecasts are evaluated honestly against standard baselines. A pre-trained checkpoint is provided solely so that participants on constrained hardware can follow the tutorial without training.
- **Primary intended users:** tutorial participants — climate and ocean scientists learning graph ML, and ML practitioners learning climate forecasting practice — and students or researchers extending the notebook.
- **Out-of-scope uses:** operational marine heatwave early warning, or any management, conservation, commercial, or policy decision. The model is a monthly, ~2°-resolution research demonstration; it does not resolve the daily timing or fine spatial structure of marine heatwave events and systematically under-predicts extremes (see Caveats).

## Factors

- **Geography:** skill varies strongly by region. Relative to persistence, skill is generally higher in regions of persistent ocean currents and lower in equatorial waters and near the sea-ice margin (where the underlying data product itself is least reliable).
- **Lead time:** forecasts are produced recursively beyond one month; errors compound and skill decays toward the climatological error with increasing lead.
- **Anomaly magnitude:** performance differs between ordinary months and extreme-anomaly months, with extremes damped toward the mean.

## Metrics

Root-mean-square error (RMSE, °C) of 1-month-ahead SSTA forecasts over the test period, pooled over nodes; per-node skill relative to persistence, 1 − RMSE_GNN/RMSE_persistence; and RMSE as a function of lead time (1–12 months), averaged over all ~110 test-period initializations with model, persistence, and climatology verified on identical target months.

## Training Data

NOAA Extended Reconstructed SST v5 (ERSSTv5; Huang et al., 2017): global monthly mean SST on a 2° × 2° grid, subset to 64°S–62°N (sea-ice-affected polar oceans excluded), January 1950 – December 2009 (720 months) for training. Anomalies are computed against a 1980–2009 monthly climatology derived from the training period only, so no validation- or test-period information enters preprocessing. The correlation graph is likewise constructed from training-period data only.

## Evaluation Data

Chronologically held-out ERSSTv5 data from the same grid: validation January 2010 – December 2015 (model selection); test January 2016 – September 2026 (129 verifying months, entirely unseen).

## Quantitative Analyses

On the test period (1-month lead): **GNN RMSE 0.322 °C**, against **persistence 0.344 °C** and **training-period climatology 0.744 °C**; the GNN outperforms persistence at **85% of ocean nodes**. Per-node skill maps, forecast time series at four documented marine heatwave hotspots (NE Pacific "Blob", Tasman Sea, Western Australia, Niño3.4), and lead-time skill curves for leads 1–12 are reported in the notebook. Figures regenerate on execution; values quoted here correspond to the released executed notebook and will vary slightly as ERSSTv5 is extended month by month.

## Ethical Considerations

The model processes publicly available geophysical data and involves no personal or human-subject data. The salient risk is misuse of a pedagogical model as decision support: forecasts of marine heatwave precursors could in principle influence fisheries, aquaculture, or conservation decisions, and this model is not validated for such use. Energy cost of training is negligible (~1 GPU-minute).

## Caveats and Recommendations

- **Extremes are under-predicted.** MSE training produces regression toward the mean; the largest anomalies — the events most relevant to marine heatwaves — are damped. This is demonstrated explicitly in the tutorial and motivates extremes-aware losses as future work.
- **Non-stationarity.** Under a warming ocean, test-period anomalies exceed the training-period range; correlation structure learned from 1950–2009 may drift.
- **Data product limits.** ERSSTv5 is a statistically reconstructed product; variance is artificially low near the sea-ice edge, and early-period observations are sparse. Results differ somewhat from the published ERA5-based study.
- **Recursive leads compound errors** and should be interpreted against the climatological baseline, not in absolute terms.
- Users extending the model toward application should consult the "From Prototype to Practice" section of the tutorial: daily data, extremes-aware training, uncertainty quantification, and validation against operational systems are prerequisites to any real-world use.
