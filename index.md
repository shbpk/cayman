---
layout: default
---
---


## Introduction
Antimicrobials, including antibiotics, antivirals, antifungals and antiparasitics are the medicines used to prevent and treat infections in humans, animals and plants. According to the National data for the United States reveal that almost 270 million antibiotics prescriptions are written each year <a href="https://www.michiganmedicine.org/health-lab/nearly-quarter-antibiotic-prescriptions-may-be-unnecessary#:~:text=National%20data%20indicate%20that%20around,prescriptions%20are%20filled%20every%20year">[report]</a>. This is roughly a prescription for every 5 out of 6 people in the US. Antimicrobial Resistance (AMR) occurs when bacteria, viruses, fungi and parasites change over time and no longer respond to medicines making infections harder to treat and increasing the risk of disease spread, severe illness and death. As a result of drug resistance, antibiotics and other antimicrobial medicines become ineffective and infections become increasingly difficult or impossible to treat. AMR can be a serious threat  for the future generations and according the some researchers, it can be a threat more severe than cancer in 2050 as shown if the figure.



![alt text](assets/css/AMR-ONeil.png)
<center>
Predicted mortality from AMR compared to other common caualities
<a href="https://www.gavi.org/vaccineswork/what-antimicrobial-resistance-and-how-can-we-tackle-it?gclid=CjwKCAjwo7iiBhAEEiwAsIxQEe9oBkLiHuUFI8ru5pDI6lSTsba_wHPjZBYob6fX-YYfKzztvWuvEhoCdtUQAvD_BwE">[Image Source: Gravi.org]</a>
</center>


## AMR in Agriculture
The global spread of antimicrobial resistant organisms and AMR-associated genes poses a serious threat to the safety of both human and natural systems, increasing the hospitalization and mortality rates of both humans and production animals <a href="#1"><sup>1</sup></a>. In particular, the release of ARGs and organisms into the environment from agricultural sources is considered a serious health threat <a href="#2"><sup>2</sup></a>. For example, antibiotic treatments have been observed to cause increases in the abundance of ARGs in animals, which leads to concomitant ARG prevalence in manure from antibiotic-treated animals <a href="#3"><sup>3</sup></a>. Elevated concentrations of antibiotics and ARGs have also been found in or near livestock production facilities <a href="#4"><sup>4</sup></a>. Moreover, land application of manure has been observed to result in transient increases in ARG abundance and populations of resistant zoonotic microorganisms <a href="#5"><sup>5</sup></a>. In sum, the joint occurrence of a large number of farm animals receiving antibiotics and dependence on shared soil and water resources makes animal agriculture and farms important potential contributors to antibiotic resistance observed in clinical settings <a href="#6"><sup>6</sup></a>.

There can be various pathways antimicrobial resistance in the environment. One of the hypothesized pathway is illustrated in the figure below.

<p align="center">
  <img width="70%"  src="assets\AgAMRCycl.png">
</p>
<center>A hypothetical AMR cyle in agricultural environment</center>

Antibiotics administered to animals for various reasons are not metabolized completely and aree found undigested in their manure. Applying manure for better soil health resulting to better crops is a common practices around the world. This can be an environment where bacteria can develope resistance to the antibiotics and reach human through water uptake by plants or instream water.

Tylosin is an antibiotic drug commonly used in veterinary medicine to treat a wide range of bacterial infections in animals, particularly in poultry, swine, and cattle. Tylosin works by inhibiting bacterial protein synthesis, which prevents the growth and spread of the bacteria <a href="#7"><sup>7</sup></a>.

Enterocci is a bacteria found in human intestine and egricultural environment <a href="#8"><sup>8</sup></a> and have shown tendency to develop resistance to antibiotics.

## Objective
 The objective of this study was to deduce a relationship between the presence of enterococci, a bacteria found in human intestine and egricultural environment <a href="#8"><sup>8</sup></a>, and it's mutated variant having tylosin resistance, the tylosin resistance eterrocci. 

This will provide an evidence of tylosic resistance bacteria in agricultural watersheds where enterocci is found if a strong relationship is found.

## Material and Methods
### Study Area
The data comprises of observed water quality data from the Black Halk Lake (BHL) watershed in SAC county-IA. The Black Hawk Lake watershed catalouged as HUC12 level by the USEPA is a small watershed (shown is figure below) within the North Raccoon River (HUC-8) and Indian Creek-North Raccoon River (HUC-10) watersheds.

<p align="center">
  <img width="70%"  src="assets\bhl.png">
</p>
<center>Study area, the Black Hawk Lake Watershed</center>

### Data
Observed data includes grab sampling from 5 different locations within the BHL watershed done every two week since 2018. The samples are bacteria plated to check for the presence of enterrocci and its tylosin resistant variant along with other water quality paramterets like total nitrogen, and phosphorous, etc. The data analzyed in this study also consists of climatic variables of the sampling week, i.e., total precipiation, and the average temperature of the week when sampling was done. Sample of the data analyzed is shown below:

| `Date` | `ent` | `tet_ent` | `tyl_ent` | `ecoli` | `Precip` |	`Precip-1` | `Temp` | `Temp-1` | `TSS` |	`DRP` |	`TP`	| `TN`	| `Avg_Flow` |
|:-----|:-----|:-----|:-----|:-----|:-----|:------|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|18/03/2021	|87|22|5|120|0|1|55|60|80|244|22|66|0.03|
|25/03/2021	|90|18|2|99|3|0|66|66|88|279|23|80|0.08|

The variables are described as follows

| Variable        | Description          | Unit |
|:-------------|:------------------|:------|
| `Date`           | day of sampling | Date  |
| `ent`           | Amount to enterocci | Colonies per 100 ml of sample  |
| `tet_ent`           | Amount of tetracycline resistant enterococci | Colonies per 100 ml of sample  |
| `tyl_ent`           | Amount of tylosin resistant enterococci | Colonies per 100 ml of sample  |
| `ecoli`           | Amount of Ecoli. | Colonies per 100 ml of sample  |
| `Precip`           | Total rainfall during the sampling week | inch  |
| `Precip-1`           | Total rainfall in previous week | inch  |
| `Temp`           | Average temperature od sampling week | Degrees farenheit  |
| `Temp-1`           | Average temperature of previous week | Degrees farenheit  |
| `TSS`           | Total suspended solids  | mg/L|
| `DRP`           | Dissolved reactive phosphorous  | mg/L|
| `TP`           | Total phosphorous  | mg/L|
| `TN`           | Total nitrogen  | mg/L|
| `Avg_Flow`           | Average flow of the sampling week  | mg/L|


# Analyses
The study uses machine learning approach to develop a model to predict tylosin resitant bacteria in an agricultural watershed. Two model are used in this study, `1- Linear regression to treat data ignoring timeseries behavious`, and `2- XGBoost regressor considering timeseries`. Analyzed dataset is available in the  <a href="https://github.com/shbpk/ABE516_TP">GitHub repository</a> along with the interactive python notebooks.

[`View full code for Linear Regression`](https://github.com/shbpk/ABE516_TP/blob/ffbdd114018512647dde6a179ecf72b358a17891/Notebooks/Term%20Project%20LR.ipynb)

[`View full code for XGBoost Regression`](https://github.com/shbpk/ABE516_TP/blob/ffbdd114018512647dde6a179ecf72b358a17891/Notebooks/Term%20Project%20XGBR.ipynb)

The analyses starts with eliminating the null values or substituting them with a legitimate assumption, executing their descriptive analysis and scatter plot to understand the data. Scatter plot of the predicted variable "`tet_ent`" with other variables is shown below.


<p align="center">
  <img width="100%"  src="assets\LR_Plot.png">
</p>
<center>Scatter plot of the variables</center>

The variable, formatted and cleaned treated with the linear regression model library from sckikitlearn and also the XGBoost regressor.

### Methodology Flowchart

<iframe frameborder="0" style="width:100%;height:900px;" src="https://viewer.diagrams.net/?tags=%7B%7D&highlight=0000ff&edit=_blank&layers=1&nav=1#R7VzZctu4Ev0aVyUPUnERZenR8nYzYyeZyNmepiASonBNEgxAbfn6aSzcKUuiRdv31iSVhGhi7T7oPmjQObMvw80tQ%2FHinno4OLMMb3NmX51Z1vh8CH8LwVYJhqatBD4jnhKZuWBKfmMtNLR0STzMSxUTSoOExGWhS6MIu0lJhhij63K1OQ3Ko8bIxzXB1EVBXfqdeMlCSR1jnMv%2Fg4m%2F0COfO3reIUrragFfII%2BuCyL7%2Bsy%2BZJQm6incXOJAqC5Vy%2FcP2%2B%2FB3ePw9o%2B%2F%2BC%2F0dfLnw8dvPdXZzTFNshUwHCWtu%2Bb3t9bdx6m5daLf9%2F4fFwtrfaWbGCsULLW6zqxhAINMPLKCR188pqJZKriOVoTRKITpIDHEFUpQWgkmMKs2BFlDd1Jk8GSrLTX8tRSqnMxplPS4xNEFVBjFG9VIv652I6o%2Fp5933xAjaAaNrUuodkmDZRhxVXjYxvh9YRVqrOcs7vnrMK0dC5kmDKMQatwEAFM5f0v94%2FJV%2B0WceJZfEInmSCDzjU7wAYcxZihZMo2IQds5WqV5WOA%2FYvEI%2BxjWjwPqMzCXPYHRSIgTzKrvPucvJusFSfA0Rq7oYQ2OGmSLJAygZIrFkQ1Ofa8qBwEgmTI5tD2fzy3XBTlPGH3EhTfecDZ0htl09%2FoY7YtWmCV4U3Cw2ufcYgozZluokr7VLkZHD0eV1rkntmxdY1HywjoAaOfvZ%2F3mHg4etJM7wuFZrRyecnDGd4YiPyCR35mzM80TebudHX3lAGvjM4o80C1EdbWyOcANy%2BjKRO%2FbyF2Agye%2F5VpFaE5ItKRL0QJawt8RjXolseiI44T34VmNQeci1AOCexyAjGVb32fYR4nqdr6M3IRQ4WxP6GFfXKMZWljDxLuMGDxGUWOTGXIffUaXkQc2kltdLIBEJCEQr1t1eagyPi2TeJlk1l8QLrvDMZe7Xm5QgRuIAhIQUrDSEZjLWYrGEa5jc03AZUBnqiSAJfoVePtWai9XGQgXtEArhTQeCq%2FKCs0K05mJ7hB4NGCCAO0bdxkuA5SIZ2CqsDAUCm8bzXgsF2qISa0xfsw2Q7KgEvHZeC5FjJfGUzGE9HFfPYWUyVUspL7zHi8r8%2FIITzeNnNxaOslsblpT6WxclzIPphBshVpuSFSgZwU9Fq0g6n2YaL7DUwoxzyiEVowYrxoYWSmUJ1SRQZgxp8FKThEeiCdU%2Fe5hOn1frseXPMaR11BPzP2ByLkGsHhZww0IEHJcAcu7fAqpKfJJvm8yndQ6CjiVUHGDpZpAbphVxgaNs2vrbGScjS8FJfgbppIKrjJPqRWfvhiR9GlcsaOYV7orao0gqqbN%2BgUnoTZjzXc0iRt9z1NkRHoH7Gm6sJddlNmEI343sYmh%2FKXdRUGufin%2F4gI%2B7%2FBcBHqzIPqig7%2BUdUVGrFGZjZw30BGrgY7YnfEReycfyYjFR7zON%2FGN2sRPWD1rJ7ZQFnkjsZ%2FFnpfKylxbpRu8AoXzoidTeytZNIwpuKqkp7y60dTekI1SsEvgbzFi%2Ffqu3MGThfufJlR6n%2BcSYA%2Fh0byRAA%2FdEZ7NxRvd2Hg5MmydG3X8GQ34G3UGP7Omfuz5eKqLlEFo8ymEketcOsl9h9BVXueO0lir%2F784SbbaHGgJUCsZC29I8kM07zu69LPw5mqje5aFbVqIYL0%2FioWfeQ%2BimDeTpbTdcabkdMlc%2FITCtCESxHycPFHvXNUTynwSGAwD1SCrcq6qycy66WdKJF3VgBqWAWWfj8s9qHnqRjlWLhhD20K1WFTgu4exm4e5Oaz6QMM3B6oaP4dtppD2SHYaHGkV2UFAYn6AM0HATGQmUnqVhgA4cnHzcXo2cgbOC3oQezSqeZDBoO5AUtnJHciw1Xl6mgDoeUJcyQQvwHdsOeFNQUxEPsxdRmK5Sywja8p3MZ3a8JIZHlhXh9lvhC9RQH4jcT49mlIZR1Mqz8Ejb9CEqJE1s4ddJmjGFUQN65zIdBpiUtru5JA637%2BT2YKGsyVvz1x38tOdjLYr9Vc8uGPUKcGwQfvDrrQ%2FfnpDN2Ub4MyJWTHTAGeod71eUf7%2B6czJifvVmzj3K2nu4B65CyJPzHdARSNFcfWN16kyeidQB%2Buo45deCEkFlwHiMjkTzlCAIldYQNoFb0SkxUX%2FnDXqCRPGsczkTO8%2FPVzL44hPGdgyfE3bvI5SP19e6FMbbGBwQmQuFMOJH5E5BFLJv4pHMpVJU4cwH2KnKOkk7Zl98y%2B2W44nEakcRw3mP24nlHJhCHUC%2FoJ9hjkvUwiyb%2BYnpBVvMN6Nq2eDerwbmA0Bzxx0dQY2d1%2BCx43gCeFQRaJeIk67AjpGrJmqfjGjSULD5neBzHzJN7A%2F5RuPMCzvQZQ8SJiSLyPiQmjqzYhH1CsczuRxRKgLgNqbMYwe1auIsnBPbj%2BLaxf3X6DFDYVhEU8OD4JxNxh9xcPUyOw7JTgOBw0ZGev8BfmXPTjgIBt5F%2BLLGCi5IrISt6zhsjnyzEmeLPlZypU0Z07aZGmOs9TebIsmo3uzLekW3ptuWRe%2FAKpbNZU9MytjG5U0s13xXWrhtbRMrSOnmt8ZH5bfOVVSxW463r8yGE2zgEajPx6PnkSkKBQ%2BpOgCpfaBKHXeFEidSippYFew1Rqko5cF6cDaD9L0ToGE6jahgE8RLkQi6g7NcPCZcqJC8VUaxbMKFwFwbXgh4%2F5E9nSRJgobs4Z6MBjUF9fKAQHEgQZubuHs%2BbdpjTbwpx%2BL8NtNeBs4FQuPG4Kb03cawpt9gvD2l2f%2F%2BmGN%2BKrHjO3k6ufgfvOt4b7rgoszDMi%2BRuTXUpxWPlylB50pCmNxFbvDmgu8Qb4wVukbKi3NNr11CCUp3x51ZZHq%2FeOB149OV9Y4JGn%2Bf8I19npnq9E7l93%2Fbki%2FGtWoIqol06j2M6z0czof3qjDA3K%2BrYE4duyz8pWhcb4PjqJUZQ05Rg3DKnGQ4eC1KYh1IMjtN0VBavfh45borWbRrWqyoGP4NiXNnwdfjTWzb1iDEtYGCs1Hge1t3Z3XPOxe1A5fE6SDCokyWmK0es9W9dSng%2BiXP1afHu%2B2H%2F3V6M9ROL0ldz8%2BtfxJjwlyAUZE3KY844c8OvtsNf9y0Wn6SL%2Fdl3K7tbK36Q6e%2Bpa%2F%2BK%2BR10M3%2FKGfKDQdOrr65L8R%2BWYr5J%2FwZ5yO%2FzmjF99IH5cJI%2BrbPzEf%2B9Dd9O8G2L8BzPPBK%2B%2BApo9Md9OTSHxT%2FgQ32RHF2yrthahmJReSnbOPpprVpEqln47D%2BHG3A%2FtMmdHMEsVMj%2BBPHbtbmv8Almi8KkyM5uD1P4aS4%2FI6nW74ssV3U9O3YnFzdCKTm9Ucasc2P%2B6q5lDPINIn5QPo0Gp74dIdgl43tFQQlH3V%2F1wE1WJUxwjqLgnXy3JmefLBdPalHxqzcM%2BE0mFp4LfCUkzbagclc7AHk62hBMX8v7xQ1fP%2FNsS%2B%2Fgc%3D"></iframe>


# Results
## Linear Regression Analysis

### Model Performance

|Statitics|.|.|.|
|:-------|:-----|:-----|:-----|
|Dep. Variable:|      tet_ent|   R-squared:|         0.859|
|F-statistic:|       393.9|   Adj. R-squared:|       0.857|
|No. Observations:|     330|   Prob (F-statistic):     |2.51e-135|


### Coefficients and Their Significance

|Predictor                 |Coefficent    |Standard Error          |t-statistic      |Probability>t      |Confidence Intervals I 95%[0.025      0.975]|
|:----|:-----|:-----|:-----|:------|:------|
|Intercept    |-16.9269      |8.953     |-1.891      |0.060     |-34.540    ~   0.686|
|ent            |0.0170      |0.005      |3.536      |0.000       |0.008 ~      0.026|
|ecoli          |0.0307      |0.003     |10.171      |0.000       |0.025 ~      0.037|
|tyl_ent        |1.0604      |0.097     |10.906      |0.000       |0.869 ~       1.252|
|Precip        |65.0207      |9.205      |7.064      |0.000      |46.911 ~     83.130|
|Temp           |0.2425      v0.150      |1.611      |0.108      |-0.054 ~       0.539|


## XGBoost Regression

<p align="center">
  <img width="70%"  src="assets\xgbr_out.png">
</p>
<center>Significance of variables for XGBoost Model</center>


`R-Squared for XGBoost Model = 0.914`

# Refernces
<p id="1">1- Allen, H. K.; Donato, J.; Wang, H. H.; Cloud-Hansen, K. A.; Davies, J.; Handelsman, J., Call of the wild: antibiotic resistance genes in natural environments. Nat. Rev. Microbiol. 2010, 8, (4), 251-259.</p>

<p id="2">2- PCAST Report to the President on Combating Antibiotic Resistance; Executive Office of the President of the United States: 2014, 2014; p 78.</p>

<p id="3">3- Holman, D. B.; Chénier, M. R., Impact of subtherapeutic administration of tylosin and chlortetracycline on antimicrobial resistance in farrow-to-finish swine. FEMS Microbiol. Ecol. 2013, 85, (1), 1-13.</p>

<p id="4">4- Chee-Sanford, J. C.; Mackie, R. I.; Koike, S.; Krapac, I. G.; Lin, Y.-F.; Yannarell, A. C.; Maxwell, S.; Aminov, R. I., Fate and transport of antibiotic residues and antibiotic resistance genes following land application of manure waste. J. Environ. Qual. 2009, 38, (3), 1086-1108.</p>

<p id="5">5- Heuer, H.; Schmitt, H.; Smalla, K., Antibiotic resistance gene spread due to manure application on agricultural fields. Curr. Opin. Microbiol. 2011, 14, (3), 236-243.</p>

<p id="6">6- McEwen, S. A.; Fedorka-Cray, P. J., Antimicrobial use and resistance in animals. Clin. Infect. Dis. 2002, 34 Suppl 3, S93-S106.</p>

<p id="7">7- Suchodolski, Jan S., Scot E. Dowd, Elias Westermarck, Jörg M. Steiner, Randy D. Wolcott, Thomas Spillmann, and Jaana A. Harmoinen. "The effect of the macrolide antibiotic tylosin on microbial diversity in the canine small intestine as demonstrated by massive parallel 16S rRNA gene sequencing." BMC microbiology 9, no. 1 (2009): 1-16.</p>

<p id="8">8- Ramos, Sónia, Vanessa Silva, Maria de Lurdes Enes Dapkevicius, Manuela Caniça, María Teresa Tejedor-Junco, Gilberto Igrejas, and Patrícia Poeta. "Escherichia coli as commensal and pathogenic bacteria among food-producing animals: Health implications of extended spectrum β-lactamase (ESBL) production." Animals 10, no. 12 (2020): 2239.</p>

<a href="#TOP">Back to top</a>


