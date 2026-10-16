# Carbon Emissions and Computational Sustainability

> **Fill this template to the best of your abilities**
>
> Use the [CodeCarbon](https://codecarbon.io/) library or an equivalent carbon emissions tracking library (some examples include [carbon tracker](https://github.com/saintslab/carbontracker), [experiment impact tracker](https://github.com/Breakend/experiment-impact-tracker), and  [Eco2AI](https://github.com/sb-ai-lab/Eco2AI), among others) to estimate carbon emissions
> associated with your tutorial especially if it involved model training, fine-tuning, hyperparameter search, benchmarking,
> substantial inference, data processing, or other computation. For an example of how to use CodeCarbon please refer to the
> following Hanna et. al, CCAI Tutorial: 
> [_Reducing Your Climate Impact When Training Machine Learning Models (2026)_](https://colab.research.google.com/github/climatechange-ai-tutorials/tracking-ml-emissions/blob/main/Tracking_Emissions_from_ML_Models_(Revised).ipynb)]
>
> Report to your best ability. If a value was not measured or cannot be
> reasonably estimated, write **Not measured**, **Unknown**, or
> **Not applicable** rather than guessing. If using CodeCarbon, you may leave output `emissions.csv` generated in the parent directory `emissions-reporting`.
>
> Your work in carbon emissions reporting will be a part of a pilot program with CCAI as part of a broader effort to improve reporting best practices.
> For Round II tutorial review, we ask all authors to report operational carbon emissions at a minimum. 
> Sections pertaining to embodied emissions as well as idle consumption emissions estimates for water usage are exploratory and we appreciate you answering to the
> best of your abilities.
> In sections that overlap in `model-card/MODEL_CARD.md` and `datasheet/DATASHEET.md` with emissions reporting, you may place a note rerouting readers to this file.

---

## 1. Computation included

### What computation did you perform?

Select all that apply:

- [ ] Data preprocessing
- [ ] Model training
- [ ] Model fine-tuning
- [ ] Hyperparameter tuning
- [ ] Model evaluation or benchmarking
- [ ] Model inference
- [ ] Complete notebook execution
- [ ] Other: [Describe]

### What is included in the energy and emissions reported below?

Select all that apply:

- [ ] Data preprocessing
- [ ] Model training
- [ ] Model fine-tuning
- [ ] Hyperparameter tuning
- [ ] Model evaluation or benchmarking
- [ ] Model inference
- [ ] Complete notebook execution
- [ ] Other: [Describe]

**Briefly explain what was tracked:**

[Example: CodeCarbon tracked data preprocessing, 10 hyperparameter
trials, final model training, and model evaluation.]

### What is not included?

[Example: Early exploratory experiments were completed before
tracking was enabled.]

If everything was tracked, write **None known**.

---

## 2. Hardware and computing environment
**Computing environment:**

- [ ] Personal computer or workstation
- [ ] Institutional server
- [ ] Computing cluster
- [ ] Cloud system
- [ ] Google Colab
- [ ] Other: [Describe]

**CPU:**  
[Model / Unknown]

**GPU or other accelerator:**  
[Model and number / None / Unknown]

**RAM:**  
[Amount / Unknown]

**Computing provider:**  
[Provider / Not applicable]

**Computing location or cloud region:**  
[Location / Unknown]

> Report the hardware that performed the computation. Location is
> useful because electricity can have different carbon emissions
> depending on where it is generated.

---

## 3. Operational carbon emissions (Required)

### How were emissions tracked?

- [ ] CodeCarbon
- [ ] Another tracking tool
- [ ] Cloud or system information
- [ ] Not measured
- [ ] Not applicable

**Tool:**  
[CodeCarbon / Other / Not measured]

**Tool version:**  
[Version / Unknown]

**Number of runs included:**  
[Number]

**Total computing time:**  
[Hours / Not measured]

**Energy used:**  
[kWh / Not measured]

**Carbon emissions:**  
[kg CO2e / Not measured]

**Source used to determine the carbon emissions of the electricity:**  
[CodeCarbon / provider / electricity-grid data / Unknown]

> If you use CodeCarbon, report the values produced by the tracked
> experiment and record the version you used. Keep the units with
> the reported values.

---

## 4. Embodied Emissions (Report if possible)

Computer hardware also has an environmental cost from its
manufacture and production. These emissions are separate from the
electricity used while running your code.

**Were these emissions estimated?**

- [ ] Yes
- [ ] No
- [ ] Not applicable

If yes:

**Estimated emissions assigned to this work:**  
[kg CO2e]

**Source or method:**  
[Source]

**How was the estimate assigned to this project?**  
[Brief explanation]

> If you do not have enough information to make a reasonable
> estimate, select **No**.


---

## 5. Idle Consumption emissions: Water use (Report if possible)

**Was water use estimated?**

- [ ] Yes
- [ ] No
- [ ] Not applicable

If yes:

**Estimated water use:**  
[Liters]

**Source or method:**  
[Source]

**What does the estimate include?**

- [ ] Data-center cooling
- [ ] Water associated with electricity generation
- [ ] Both
- [ ] Unknown

> Water use can vary by location and computing infrastructure.
> Report the source or method used for the estimate. If reliable
> information is unavailable, select **No**.

---

## 6. Reducing computational impact (Required)

What did you do to reduce unnecessary computation?

Select all that apply:

- [ ] Reused a pretrained model
- [ ] Used a simpler or smaller model
- [ ] Used early stopping
- [ ] Reduced hyperparameter trials
- [ ] Used a more efficient hyperparameter search
- [ ] Reduced repeated experiments
- [ ] Reused cached or previously computed results
- [ ] Used more efficient hardware
- [ ] Used a lower-carbon computing location or time
- [ ] Reduced unnecessary inference
- [ ] Other: [Describe]
- [ ] No specific reduction strategy was used

**Briefly explain the most important action taken:**

[2–3 sentences]

> Report actions you actually took. If possible, say how they
> affected runtime, number of experiments, energy use, or emissions.


---

## 7. Effect on model performance

Did reducing computation affect model performance or the
educational outcome?

- [ ] Yes
- [ ] No meaningful difference observed
- [ ] Not evaluated
- [ ] Not applicable

**What changed?**

[Example: Reducing the hyperparameter search from 50 trials to 15
reduced computing time while producing similar model accuracy.]

> When possible, explain both the computational savings and any
> change in model performance.

---

## 8. Limitations (Required)

What is missing or uncertain in the reported values?

Select all that apply:

- [ ] Some experimental runs were not tracked
- [ ] Hardware energy use was estimated
- [ ] Exact computing location was unknown
- [ ] Electricity carbon emissions were estimated
- [ ] Data-center energy use was not fully included
- [ ] Hardware-production emissions were not estimated
- [ ] Water use was not estimated
- [ ] Remote AI-service infrastructure could not be measured
- [ ] Other: 