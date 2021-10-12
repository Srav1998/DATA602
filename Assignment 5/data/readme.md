
### This dataset was downloaded from [https://www.icpsr.umich.edu/web/NACJD/studies/36399]
## **Dataset Description**
1. **STUDYNO**: ICPSR STUDY NUMBER
2. **EDITION:** ICPSR EDITION NUMBER
3. **PART**: ICPSR PART NUMBER-4
4. **IDNO:** ICPSR SEQUENTIAL CASE ID NUMBER
5. **FIPS_ST**: FIPS STATE CODE
6. **FIPS_CTY:** FIPS COUNTY CODE
7. **CPOPARST:** TOT CNTY POPULATION-AGENCIES RPRT ARRSTS
8. **CPOPCRIM:** COUNTY POPULATION-AGENCIES REPORT CRIMES
9. **AG_ARRST:** NMBR OF AGENCIES IN CNTY REPORT ARRESTS
11. **AG_OFF:** NMBR OF AGENCIES IN COUNTY REPORT CRIMES
12. **COVIND:** COVERAGE INDICATOR
13. **VIOL:** TOTAL VIOLENT CRIMES
14. **PROPERTY:** TOTAL PROPERTY CRIMES
15. **MURDER:** MURDERS
16. **RAPE:** RAPES 
17. **ROBBERY:** ROBBERIES
18. **AGASSLT:** AGGRAVATED ASSAULTS
19. **BURGLRY:** BURGLARIES
20. **LARCENY:** LARCENIES
21. **MVTHEFT:** MOTOR VEHICLE THEFTS 
22. **ARSON:** ARSONS
23. **COUNTY_NAME** : Name of the county.
24. **CRIME_RATE_PER_100000** : crime rate per 100000 of population.
#### **Summary:** This data collection contains county-level counts of arrests and offenses for Part I offenses (murder, rape, robbery, aggravated assault, burglary, larceny, auto theft, and arson) and counts of arrests for Part II offenses (forgery, fraud, embezzlement, vandalism, weapons violations, sex offenses, drug and alcohol abuse violations, gambling, vagrancy, curfew violations, and runaways).
####  I do not need the "'county_name','index', 'EDITION', 'PART','IDNO', 'CPOPARST', 'CPOPCRIM' 'AG_ARRST', 'AG_OFF', 'COVIND', 'INDEX','MODINDX','FIPS_ST','FIPS_CTY' " columns since they are not helpful for regression.So I dropped these columns.
