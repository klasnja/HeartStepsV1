# HeartStepsV1
Data from the HeartSteps V1 study

## Sources
**Creators**: Predrag Klasnja, Susan Murphy, Eric Hekler, Ambuj Tewari, Lisa Jackson, Shawna Smith, Andy Lee, Nick Seewald  
**Latest version by**: Eura Shin and Sorawit Saengkyongam

The authors use Lisa Gotzian's documentation as a template.

## Citation
If you utilize the HeartSteps data in your research, please cite the following reference:

Klasnja, P., Smith, S., Seewald, N. J., Lee, A., Hall, K., Luers, B., Hekler, E. B., & Murphy, S. A. (2019). Efficacy of Contextually Tailored Suggestions for Physical Activity: A Micro-randomized Optimization Trial of HeartSteps. Annals of Behavioral Medicine, 53(6), 573–582. https://doi.org/10.1093/abm/kay067

BibTex:
```
@article{heartstepsv1,
  title={Efficacy of contextually tailored suggestions for physical activity: a micro-randomized optimization trial of HeartSteps},
  author={Klasnja, Predrag and Smith, Shawna and Seewald, Nicholas J and Lee, Andy and Hall, Kelly and Luers, Brook and Hekler, Eric B and Murphy, Susan A},
  journal={Annals of Behavioral Medicine},
  volume={53},
  number={6},
  pages={573--582},
  year={2019}
}
```

<!-- The data was collected during a mobile health intervention with the HeartSteps app and combines tracker data with the Jawbone tracker and the phone accelerometer ("Google Fit") as well as local weather data.
The current dataset is based on `analysis.RData` and `csv.RData` retrieved from the shared Mbox among the team (link not shared to the public).

* initial documentation of `analysis.RData` and `csv.RData`: https://github.com/StatisticalReinforcementLearningLab/HeartstepsV1Code/wiki/C-Analysis-data-frames

* the current dataset was created by running `build_heartsteps_data.R` on `analysis.RData` and `csv.RData`
 -->
 
## Past usage
* **Reinforcement Learning & Contextual Bandits**  
    - Saengkyongam S., Pfister N., Klasnja P., Murphy S., Peters J.  (2023). Effect-Invariant Mechanisms for Policy Generalization. ArXiv preprint arXiv:2306.10983.
    - Liao, P., Greenewald, K., Klasnja, P., & Murphy, S. (2020). Personalized HeartSteps: A Reinforcement Learning Algorithm for Optimizing Physical Activity. Proceedings of the ACM on Interactive, Mobile, Wearable and Ubiquitous Technologies, 4(1), 1–22. https://doi.org/10.1145/3381007

  - Greenewald K, Tewari A, Klasnja P, Murphy S. Action Centered Contextual Bandits. Advances in Neural Information Processing Systems. 2017 Dec;30:5973-5981.

* **MRTs Methods and Development**  
  
    - Qian, T., Walton, A. E., Collins, L. M., Klasnja, P., Lanza, S. T., Nahum-Shani, I., Rabbi, M., Russell, M. A., Walton, M. A., Yoo, H., & Murphy, S. A. (2022). The microrandomized trial for developing digital interventions: Experimental design and data analysis considerations. Psychological Methods, 27(5), 874–894. https://doi.org/10.1037/met0000283
    - Qian, T., Yoo, H., Klasnja, P., Almirall, D., & Murphy, S. A. (2021). Estimating time-varying causal excursion effects in mobile health with binary outcomes. Biometrika, 108(3), 507–527. https://doi.org/10.1093/biomet/asaa070
    - Liao, P., Klasnja, P., Tewari, A., and Murphy, S. A. (2016) Sample size calculations for micro‐randomized trials in mHealth. Statist. Med., 35: 1944– 1971. doi: 10.1002sim.6847.
    - Luers, B., Klasnja, P., & Murphy, S. (2018). Standardized Effect Sizes for Preventive Mobile Health Interventions in Micro-randomized Trials. Prev Sci. https://doi.org/10.1007/s11121-017-0862-5
    - Qian, T., Klasnja, P., & Murphy, S. A. (2020). Linear Mixed Models with Endogenous Covariates: Modeling Sequential Treatment Effects with Application to a Mobile Health Study. Statistical Science, 35(3), 375–390. https://doi.org/10.1214/19-STS720
    - Dempsey, W., Liao, P., Kumar, S., & Murphy, S. A. (2020). The stratified micro-randomized trial design: Sample size considerations for testing nested causal effects of time-varying treatments. The Annals of Applied Statistics, 14(2), 661–684. https://doi.org/10.1214/19-AOAS1293



* **mHealth Data Collection Considerations**  
    - Seewald, N.J., Smith, S.N., Lee, A.J. et al. Practical Considerations for Data Collection and Management in Mobile Health Micro-randomized Trials. Stat Biosci 11, 355–370 (2019). https://doi.org/10.1007/s12561-018-09228-w





## About the dataset
1. HeartSteps is an mHealth intervention that encourages regular walking via activity suggestions tailored to the individuals’ current context.  
1. 6-week micro-randomized trial with 37 participants, notifications could be sent at each of 5 user-specific times/day  
1. includes the following dataframes: 
* [documentation for `users.csv`](https://github.com/klasnja/HeartStepsV1/wiki/Documentation-for-users.csv), a 37x117 dataframe  
  **identifier**: *user.index*
* [documentation for `suggestions.csv`](https://github.com/klasnja/HeartStepsV1/wiki/Documentation-for-suggestions.csv), a 8,274x86 dataframe  
  **identifier**: *user.index* and *decision.index*
* [documentation for `jbsteps.csv` and `gfsteps.csv`](https://github.com/klasnja/HeartStepsV1/wiki/Documentation-for-jawbone.csv), a 197,524x7 dataframe for steps from the phone accelerometer ("Google Fit") and a 237865x10 dataframe for steps from the  jawbone tracker   
  **identifier**: *user.index*, *decision.index* and *steps.utime*


## The tables

### [Users](https://github.com/klasnja/HeartStepsV1/wiki/Documentation-for-users.csv)
[`users.csv`](https://github.com/klasnja/HeartStepsV1/blob/main/data_files/users.csv) is a 37x117 data frame that contains demographic information on the participants as well as the results of the intake and exit surveys. Participants were interviewed before the study and after completing it. The exit survey re-administers the activity choice index, self-efficacy for physical activity and the IPAQ. The surveys collected data on the following topics:
* Demographic data
* Mobile phone use
* Walking environment at work
* Conscientiousness
* Activity Choice Index (intake and exit)
* Self-Efficacy for Physical Activity (intake and exit)
* International Prevalence Study (IPS) on Physical Activity
* International Physical Activity Questionnaire (IPAQ)(intake and exit)
* **identifier**: *user.index*



### [Suggestions](https://github.com/klasnja/HeartStepsV1/wiki/Documentation-for-suggestions.csv)
At each of five user-specific times during the day and if the user is available, then whether or not to send a notification is randomized. The walking suggestions and the responses are recorded in [`suggestions.csv`](https://github.com/klasnja/HeartStepsV1/blob/main/data_files/suggestions.csv), a 8,274x86 data frame.  
<!-- <img src="notificationflowchart.png" alt="plot" width="400" > -->

This table includes the following data:
* notification time and response time as well as the type of walking suggestion ("active" or "sedentary").
* the user's context at the time of receiving the notification
* aggregated step counts before and after the suggestions
* **identifier**: *user.index*, *ema.index* and *decision.index*

### [Steps](https://github.com/klasnja/HeartStepsV1/wiki/Documentation-for-jawbone.csv)
Using the Jawbone tracker as well as the steps measured using the phone accelerometer ("Google fit"), a participant's steps were recorded throughout the intervention. The minute-by-minute steps are recorded in [`jbsteps.csv` and `gfsteps.csv`](https://github.com/klasnja/HeartStepsV1/wiki/Documentation-for-jawbone.csv), a 197,524x7 dataframe for steps from the Google Fit information and a 237,865x10 dataframe for steps from the  Jawbone tracker dataframe for each user for each minute.  

**identifier**: *user.index*, *ema.index*, *decision.index* and *steps.utime*

<!-- # Usage
## Preliminaries for working with time in R

```
## largest number of digits used to represent fractional seconds
options(digits.secs = 6)

## number of digits in Unix time (seconds since 1970-01-01 00:00 UTC)
## + largest number of digits used to represent fractional seconds
options(digits = 10 + 6)

sys.var <- switch(Sys.info()["sysname"],
                  "Windows" = list(locale = "English",
                                   mbox = "Z:/HeartSteps/"),
                  "Darwin" = list(locale = "en_US",
                                  mbox = "/Volumes/dav/HeartSteps/"),
                  "Linux" = list(locale = "en_US.UTF-8",
                                 mbox = "~/mbox/HeartSteps/"))
## time zone identifiers are localized, so set the locale
Sys.setlocale("LC_ALL", sys.var$locale)

## arithmetic on POSIXct objects uses system time zone, so set this to UTC
Sys.setenv(TZ = "GMT")
``` -->

<!-- ## Examplary analysis of the data
To guarantee that time columns are read in as time, we recommend to use `read_csv()` from the `tidyverse` package. -->
