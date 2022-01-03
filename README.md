# WEIG dataset

This is the companion repository for the paper titled "_[Effectiveness of research grants funded by European Research
Council and Polish National Science Centre](https://doi.org/10.1016/j.joi.2021.101243)_" published in _Journal of Informetrics_ in 2022.

## Data

Data for this dataset come from 3 sources:
1. National Science Centre, Poland,
2. European Research Council,
3. Web of Science, Clarivate Analytics.

This dataset includes two files:
1. `weig.pg_dump` which is a dump of Postgres database collected and used for our research;
2. `aggregated_values.csv` which consists of aggregated metrics for each agency, panel, funding scheme, and year.

Details of data aggregation were described in the paper. Data were collected on 20 October 2021.

## Aggregated values in `aggregated_values.csv`

File `aggregated_values.csv` consists of columns:
1. Agency
2. Panel
3. Funding scheme 
4. Year in which given projects end(ed)
5. Number of projects from a given agency, panel, funding scheme, and ending year
6. Sum of Impact Factors of publications published within the scope of projects from given agency, panel, funding scheme, and ending year
7. Sum of Article Influence Score
8. Sum of Average IF Percentile
9. Funding in EUR (1 EUR = 4.3 PLN)
10. WEIG-IF
11. WEIG-AIS
12. WEIF-IF%

## Postgres database - `weig.pg_dump`

The database dump was created with the `pg_dump` command. To reconstruct database use command `psql -d newdb -f weig.pg_dump`. Before that, you probably need to create two roles in your server: `crawler` which will be an owner of all tables and `readonlyu` which will be given only select privileges on all tables.

Metrics from Journal Citation Reports collected in the `journal` table were deleted under the agreement with Web of Science Group, Clarivate Analytics.

## Licence

We grant [CC BY 4.0 license](https://creativecommons.org/licenses/by/4.0/) for the whole dataset ***except*** for the tables:
* `journal`,
* `publication`,
* `projectpublication`

in `weig.pg_dump`. For these tables, all rights are reserved for the Web of Science Group, Clarivate Analytics, as the data aggregated in these tables come directly from Web of Science Web Services Lite.

## Acknowledgements

The authors would like to thank Web of Science Group, Clarivate Analytics for giving consent for usage, aggregation, and publication of data acquired from their databases. Especially we would like to thank Radek Budzichowski and Marcin Kapczyński from CA for their commitment and openness to find solutions that satisfied both sides.

We would also like to thank Agnieszka Nowicka (Wroclaw University of Science and Technology) for the legal counsel regarding usage and publication of our data as well as Krzysztof Moskwa (WUST) and Barbara Urbańczyk (WUST) for providing expert knowledge for the counselor.

## Reference

When using this work please cite:
```
Maciej Dzieżyc, Przemysław Kazienko,
Effectiveness of research grants funded by European Research Council and Polish National Science Centre,
Journal of Informetrics,
Volume 16, Issue 1,
2022,
101243,
ISSN 1751-1577,
https://doi.org/10.1016/j.joi.2021.101243.
(https://www.sciencedirect.com/science/article/pii/S1751157721001140)
Abstract: We propose WEIG – Wroclaw Effectiveness Indicator for Grants. This new scientometric measure is an aggregated quality measure of scientific papers published with the grant support divided by its budget. Several WEIG variations have been considered with respect to journal quality indicators like Impact Factor (IF), Article Influence Score (AIS), and Average Journal Impact Factor Percentile (IF%). Projects from two public agencies were analysed utilising the WEIG measures: European Research Council (ERC) and National Science Centre, Poland (NSC). The studies revealed that NSC grants are overall more effective than ERC ones, constantly 2–3 times more for Physical Sciences and Engineering (PE). There are four NSC panels distinctively more efficient than their counterparts in ERC: Mathematics (PE1), Fundamental Constituents of Matter (PE2), Computer Science and Informatics (PE6) and Universe Sciences (PE9). The most efficient NSC funding schemes are Etiuda, Preludium, and Harmonia. The higher average effectiveness of programmes aimed at young scientists has been observed: the ERC Starting Grants have greater effectiveness than Advanced Grants. Both agencies manage to keep overall efficiency regardless of increasing their budget over the years. Limitations of the proposed approach to assess project effectiveness, especially for Social Sciences and Humanities, are also discussed.
Keywords: WEIG; Research efficiency; Research grant; Funding acknowledgement analysis; European research council; National science centre
```
BibTeX:
```bibtex
@article{Dziezyc2021Effectiveness,
title = {Effectiveness of research grants funded by European Research Council and Polish National Science Centre},
journal = {Journal of Informetrics},
volume = {16},
number = {1},
pages = {101243},
year = {2022},
issn = {1751-1577},
doi = {https://doi.org/10.1016/j.joi.2021.101243},
url = {https://www.sciencedirect.com/science/article/pii/S1751157721001140},
author = {Maciej Dzieżyc and Przemysław Kazienko},
keywords = {WEIG, Research efficiency, Research grant, Funding acknowledgement analysis, European research council, National science centre},
abstract = {We propose WEIG – Wroclaw Effectiveness Indicator for Grants. This new scientometric measure is an aggregated quality measure of scientific papers published with the grant support divided by its budget. Several WEIG variations have been considered with respect to journal quality indicators like Impact Factor (IF), Article Influence Score (AIS), and Average Journal Impact Factor Percentile (IF%). Projects from two public agencies were analysed utilising the WEIG measures: European Research Council (ERC) and National Science Centre, Poland (NSC). The studies revealed that NSC grants are overall more effective than ERC ones, constantly 2–3 times more for Physical Sciences and Engineering (PE). There are four NSC panels distinctively more efficient than their counterparts in ERC: Mathematics (PE1), Fundamental Constituents of Matter (PE2), Computer Science and Informatics (PE6) and Universe Sciences (PE9). The most efficient NSC funding schemes are Etiuda, Preludium, and Harmonia. The higher average effectiveness of programmes aimed at young scientists has been observed: the ERC Starting Grants have greater effectiveness than Advanced Grants. Both agencies manage to keep overall efficiency regardless of increasing their budget over the years. Limitations of the proposed approach to assess project effectiveness, especially for Social Sciences and Humanities, are also discussed.}
}
```