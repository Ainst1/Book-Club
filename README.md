# Simulating Seizure Termination

## Replicating dynamotype-based seizure termination with a causal phase estimator.

---

## Repository Structure
project/
├── Modified_Stimulation_Integrator.mlx # Szuromi et al. simulator with added preprocessing, causal phase estimator and saving method
├── Signal_Analysis.mlx # Analysis file of simulated data to understand it better
├── Stimulation_Validation.mlx # Creation of new paths as testing data to validate the termination method
│
├── all other files # various dependencies, no need to touch
└── README.md

---

## How and what to run
### Important note: Comments in all caps are mine and indicate which parts of the code I have worked on.

### Modified_Stimulation_Integrator.mlx 
The initialiation of every class besides 2b has been commented out. 
For running the simulations with causal phase estimate, follow the comment/uncomment instructions in lines 780-820.
The preprocessing function is called prepro() and has two different pink noise methods to switch between.
For saving a variable that is not being saved yet, uncomment it's all_... name where the data gets saved and add its name to the save() list in line 1097.
Besides that, for playing around with the base code, Szuromi et al. left it well documented.

### Signal_Analysis.mlx 
Analysis file for the simulated data.
Sections were all given a short headline.

### Stimulation_Validation.mlx 
Creation of 5 entirely new class 2b paths and subsequent comparison to the previous paths.
Results validated by treating one group of paths as the training data, and the other as testing for the phase of the stimulation.

---

## Future work
### Adapt Stimulation_Integrator.mlx further
Specifically changing the structure of the generated data so either:
1. The resting state would have oscillations
2. Instead of an extra, untouchable burst following the one where termination was attempted, having one beforehand to fit the SSPE model on before the stimulation-pulse

### Add built in anchoring point for SSPE
If possible, determine a pattern the SSPE can determine its phase values in relation to, for example having phase 0 be an amplitude peak.
