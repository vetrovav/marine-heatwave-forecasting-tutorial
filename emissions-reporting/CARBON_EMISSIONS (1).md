# Carbon Emissions and Computational Sustainability

---

## 1. Computation included

### What computation did you perform?

Select all that apply:

- [x] Data preprocessing
- [x] Model training
- [ ] Model fine-tuning
- [ ] Hyperparameter tuning
- [x] Model evaluation or benchmarking
- [x] Model inference
- [x] Complete notebook execution
- [ ] Other: [Describe]

### What is included in the energy and emissions reported below?

Select all that apply:

- [x] Data preprocessing
- [x] Model training
- [ ] Model fine-tuning
- [ ] Hyperparameter tuning
- [x] Model evaluation or benchmarking
- [x] Model inference
- [x] Complete notebook execution
- [ ] Other: [Describe]

**Briefly explain what was tracked:**

CodeCarbon tracked one complete top-to-bottom execution of the tutorial notebook on Google Colab, from a freshly provisioned runtime: data download and preprocessing (ERSSTv5, ~4,300 ocean nodes), correlation-graph construction, training of the two-layer GraphSAGE model (~36,000 parameters, 30 epochs, ~1 minute on a T4 GPU), evaluation against the persistence and climatology baselines, and the recursive multi-lead evaluation (~110 initializations × 12 leads of inference). The energy total is dominated by the GPU (1.60 of 2.15 Wh).

### What is not included?

Development and review-iteration runs performed while preparing the tutorial (before emissions tracking was enabled), and the training of the published research model of Ning et al. (2024), which predates this tutorial and is reported with its own artifacts.

---

## 2. Hardware and computing environment

**Computing environment:**

- [ ] Personal computer or workstation
- [ ] Institutional server
- [ ] Computing cluster
- [ ] Cloud system
- [x] Google Colab
- [ ] Other: [Describe]

**CPU:**
Intel(R) Xeon(R) CPU @ 2.00GHz (2 vCPUs)

**GPU or other accelerator:**
1 × NVIDIA T4 (Google Colab free tier)

**RAM:**
12.7 GB

**Computing provider:**
Google (Colab)

**Computing location or cloud region:**
Singapore (location detected by CodeCarbon)

---

## 3. Operational carbon emissions (Required)

### How were emissions tracked?

- [x] CodeCarbon
- [ ] Another tracking tool
- [ ] Cloud or system information
- [ ] Not measured
- [ ] Not applicable

**Tool:**
CodeCarbon

**Tool version:**
3.3.1

**Number of runs included:**
1 (the complete notebook execution whose outputs are saved in the released notebook)

**Total computing time:**
161.2 seconds (~0.045 hours)

**Energy used:**
0.00215 kWh (2.15 Wh; GPU 1.60 Wh, RAM 0.45 Wh, CPU 0.11 Wh)

**Carbon emissions:**
0.00101 kg CO2e (~1.0 g CO2e)

**Source used to determine the carbon emissions of the electricity:**
CodeCarbon (built-in regional electricity carbon-intensity data for the detected location)

The CodeCarbon output file is provided at `emissions-reporting/emissions.csv`.

---

## 4. Embodied Emissions (Report if possible)

**Were these emissions estimated?**

- [ ] Yes
- [x] No
- [ ] Not applicable

We do not have reliable information on the manufacturing emissions of the shared Google Colab hardware, nor a defensible basis for amortising them over a computation of roughly one GPU-minute of training within a run of well under one hour; rather than guess, we report **No**.

---

## 5. Idle Consumption emissions: Water use (Report if possible)

**Was water use estimated?**

- [ ] Yes
- [x] No
- [ ] Not applicable

Data-centre cooling and electricity-generation water use for Google Colab are location-dependent and the executing data centre is not disclosed to users; no reliable estimate was possible.

---

## 6. Reducing computational impact (Required)

What did you do to reduce unnecessary computation?

Select all that apply:

- [x] Reused a pretrained model
- [x] Used a simpler or smaller model
- [ ] Used early stopping
- [x] Reduced hyperparameter trials
- [ ] Used a more efficient hyperparameter search
- [x] Reduced repeated experiments
- [x] Reused cached or previously computed results
- [x] Used more efficient hardware
- [ ] Used a lower-carbon computing location or time
- [ ] Reduced unnecessary inference
- [ ] Other: [Describe]
- [ ] No specific reduction strategy was used

**Briefly explain the most important action taken:**

The notebook ships a pre-trained checkpoint and a `TRAIN_FROM_SCRATCH` switch, so participants on any hardware can skip training entirely — for a tutorial expected to be executed by many participants, avoiding N redundant training runs is the single largest saving. The model itself is deliberately small (~36,000 parameters; ~1 minute of training on a T4), no hyperparameter search is performed (configuration follows the published study), and all downloads are cached so re-running the notebook does not re-fetch data.

---

## 7. Effect on model performance

Did reducing computation affect model performance or the educational outcome?

- [ ] Yes
- [x] No meaningful difference observed
- [ ] Not evaluated
- [ ] Not applicable

**What changed?**

The pre-trained checkpoint is produced by the identical notebook, data, graph, and training configuration, so the skip-training path yields the same model and results as training from scratch. The small model size is itself part of the educational design: it beats the persistence baseline at 85% of ocean nodes (test RMSE 0.322 °C vs 0.344 °C for persistence) while remaining trainable live within a tutorial session.

---

## 8. Limitations (Required)

What is missing or uncertain in the reported values?

Select all that apply:

- [x] Some experimental runs were not tracked
- [ ] Hardware energy use was estimated
- [x] Exact computing location was unknown
- [x] Electricity carbon emissions were estimated
- [x] Data-center energy use was not fully included
- [x] Hardware-production emissions were not estimated
- [x] Water use was not estimated
- [ ] Remote AI-service infrastructure could not be measured
- [ ] Other:

Development iterations prior to enabling tracking were not measured; CodeCarbon estimates energy from hardware power models and location-averaged carbon intensity rather than metered data-centre values, and overheads such as cooling (PUE) are not fully captured.
