# Covid-19

Covid-19 data visualization


This notebook serves to visualize some of the data available to the current Covid 19 outbreak. The main idea was to write the code as flexible possible so that assumptions can be changed individually.

Data on Covid-19: https://github.com/CSSEGISandData/COVID-19

Sections such as the CFR and estimation of cases are highly theoretical, and results may most likely not represent the real situation.

CFR:

The first formula (cfr2) takes deaths as its nominator and uses the sum of cases and recoveries as its denominator.
The alternative formula (cfr) uses the increase of cases at time t and divides it through the rise in cases at time t - assumed timespan between diagnosis and death.

Source: https://www.worldometers.info/coronavirus/coronavirus-death-rate/

Estimation of cases:

The estimation of cases uses the number of deaths to estimate the real count of cases. The function takes in the following variables:
  
  1. data
  2. real death rate
  3. the assumed timespan between diagnosis and death
  4. days until cases double (infection rate)
  5. a decay factor 

By taking the current total numbers of death and considering the assumed real death rate, we can calculate the total cases. Since this result is from the past, we need to propagate the result by the infection rate over the assumed timespan between the diagnosis and death into the future. A decay factor can be set to account for a slowing down of cases. 
This estimation does not properly work for countries that have fewer fatalities or fewer data available on fatalities.
