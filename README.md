# Protein signaling project

### Machine Learning and Causal Inference. MSc in Data Science Methodology. Barcelona School of Economics.

Project idea contributed by Sara Magliacane (University of Amsterdam).

## Description

In this project you should attempt to conduct a causal discovery analysis of
data collected by the study of Sachs et al. (2005), where the concentration
of 11 key
[phosphorylated proteins](https://en.wikipedia.org/wiki/Protein_phosphorylation)
was measured by
[flow cytometry](https://en.wikipedia.org/wiki/Flow_cytometry) in human
[peripheral blood lymphocytes](https://en.wikipedia.org/wiki/Peripheral_blood_lymphocyte),
across different conditions. The work of Sachs et al. (2005) shows how
causal discovery methods can recover known causal relationships in
cellular signaling networks from flow cytometry data generated with
different molecular interventions. For the purpose of this project, you
may focus the analysis in the following subset of the interventions
explored in Sachs et al. (2005):

|Stimulation            | Description                         |
|-----------------------|-------------------------------------|
|α-CD3, α-CD28          | anti-CD3, anti-CD28, baseline condition, no intervention |
| α-CD3, α-CD28, AKT inhibitor | anti-CD3, anti-CD28, [AKT inhibitor](https://en.wikipedia.org/wiki/Protein_kinase_B#Akt_inhibitors) |
| α-CD3, α-CD28, G0076  | anti-CD3, anti-CD28, [G0076](https://en.wikipedia.org/wiki/Go_6976) |
| α-CD3, α-CD28, Psitectorigenin | anti-CD3, anti-CD28, [Psi-Tectorigenin](https://en.wikipedia.org/wiki/Psi-Tectorigenin) |
| α-CD3, α-CD28, U0126  | anti-CD3, anti-CD28, [U0126](https://en.wikipedia.org/wiki/U0126) |
| α-CD3, α-CD28, LY294002 | anti-CD3, anti-CD28, [LY294002](https://en.wikipedia.org/wiki/LY294002) |

In this GitHub repo you will find a CSV file for each of the previous
experimental conditions, where each row corresponds to measurements taken
from individual cells under the corresponding condition.

Using the R package [pcalg](https://cran.r-project.org/package=pcalg), you
can run the following causal discovery algorithms:

1. Run the PC algorithm, through the function `pc()`, on what we consider here as
observational data, the baseline condition dataset.

2. Run the PC algorithm, through function `pc()`, on all datasets together.

3. Run the Fast Causal Inference (FCI) algorithm, through the function `fci()`,
   on all data sets together, with default parameters.

4. Run the Joint Causal Inference (JCI) algorithm, through the function `fci()`,
   on all datasets together, but prepared to deal differently with the
   observational and the interventional data, using the arguments
   `jci="123"` and `contextVars` with appropriate values.

On the basis of the resulting DAGs, you should attempt to spot the differences
between the results of the different algorithms and, in comparison with the
results reported in Sachs (2005), try to figure out which result seems to better
match the underlying biology.

Alternatively, or additionally, you can try to reproduce some of the results of
Mooij, Magliacane and Claasen (2020, pg. 74-82), for which you will also the
data from the interventions with PMA and β2CAMP, which differently to the
previous interventions, they do not include α-CD3 and α-CD28. You can also
explore score-based methods for observational and interventional data described
as part of the [bnlearn](https://www.bnlearn.com/research/sachs05) R package,
and in the publication of Eaton and Murphy (2007).

## Submission procedure

This project has to be submitted using
[GitHub Classroom](https://classroom.github.com). This
means that you should have cloned the GitHub repo of this project
from the organization account for MLCI in the corresponding academic
year at https://github.com/mlciXXXX using the submission link
provided through Google Classroom.

Once you have cloned this GitHub repo, then you can work on it in
your local disk and _push_ your changes whenever you like, but make
sure that you have pushed the last version of your assignment before
the deadline; consult the Google Classroom if your are unsure about
the deadline. There is no _submit_ button or any other specific
submission procedure or action than just pushing your changes to your
GitHub assignment repo. When correcting the assignment, the version
available at the deadline will be retrieved. If the last update
to the repo is posterior to the deadline, then the mark of the
assignment will have a penalty.
