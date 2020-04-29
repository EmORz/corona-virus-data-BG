# corona-virus-data-BG
Simply data of infected with Corona  Virus - COVID-19 in Bulgaria!
Information is updating every day, with information by this API https://covid19.mathdro.id/api
with axios request
```
import axios from 'axios';

const url = 'https://covid19.mathdro.id/api';

export const fetchData = async (country) => {
  let changeableUrl = url;

  if (country) {
    changeableUrl = `${url}/countries/${country}`;
  }

  try {
    const { data: { confirmed, recovered, deaths, lastUpdate } } = await axios.get(changeableUrl);

    return { confirmed, recovered, deaths, lastUpdate };
  } catch (error) {
    return error;
  }
};

export const fetchDailyData = async () => {
  try {
    const { data } = await axios.get(`${url}/daily`);

    return data.map(({ confirmed, deaths, reportDate: date }) => ({ confirmed: confirmed.total, deaths: deaths.total, date }));
  } catch (error) {
    return error;
  }
};

export const fetchCountries = async () => {
  try {
    const { data: { countries } } = await axios.get(`${url}/countries`);

    return countries.map((country) => country.name);
  } catch (error) {
    return error;
  }
};
```
# Corona Virus Tracker Live Site => https://covid19statswebsite.netlify.app/
## Corona Virus Tracker SPA => https://github.com/EmORz/project_corona_tracker
### Download application 
### Setup: npm i && npm start
# Official institution in Bulgaria connect with COVID 19
Община Разград: https://razgrad.bg/%D0%BC%D0%B5%D1%80%D0%BA%D0%B8-%D0%BD%D0%B0-%D0%BE%D0%B1%D1%89%D0%B8%D0%BD%D0%B0-%D1%80%D0%B0%D0%B7%D0%B3%D1%80%D0%B0%D0%B4 
Единен информационен портал на България:
![Image of Portal](https://github.com/EmORz/corona-virus-data-BG/blob/master/Images/Portal.jpg)

https://coronavirus.bg/bg/
### Здравните власти препоръчват използването на мобино приложение за проследяване на здравният статус:
#### Сваляне от Google Play => https://play.google.com/store/apps/details?id=bg.government.virusafe
#### Сваляне от App Store => https://apps.apple.com/bg/app/virusafe/id1506362170?mt=8

# Other 
### Visual Dashboard (desktop):
https://www.arcgis.com/apps/opsdashboard/index.html#/bda7594740fd40299423467b48e9ecf6

### Visual Dashboard (mobile):
http://www.arcgis.com/apps/opsdashboard/index.html#/85320e2ea5424dfaaa75ae62e5c06e61

### Lancet Article:
An interactive web-based dashboard to track COVID-19 in real time

### Provided by Johns Hopkins University Center for Systems Science and Engineering (JHU CSSE):
https://systems.jhu.edu/

### Data Sources:
- World Health Organization (WHO): https://www.who.int/
- DXY.cn. Pneumonia. 2020. http://3g.dxy.cn/newh5/view/pneumonia.
- BNO News: https://bnonews.com/index.php/2020/02/the-latest-coronavirus-cases/
- National Health Commission of the People’s Republic of China (NHC):
http://www.nhc.gov.cn/xcs/yqtb/list_gzbd.shtml
- China CDC (CCDC): http://weekly.chinacdc.cn/news/TrackingtheEpidemic.htm
- Hong Kong Department of Health: https://www.chp.gov.hk/en/features/102465.html
- Macau Government: https://www.ssm.gov.mo/portal/
- Taiwan CDC: https://sites.google.com/cdc.gov.tw/2019ncov/taiwan?authuser=0
- US CDC: https://www.cdc.gov/coronavirus/2019-ncov/index.html
- Government of Canada: https://www.canada.ca/en/public-health/services/diseases/coronavirus.html
- Australia Government Department of Health: https://www.health.gov.au/news/coronavirus-update-at-a-glance
- European Centre for Disease Prevention and Control (ECDC): https://www.ecdc.europa.eu/en/geographical-distribution-2019-ncov-cases
- Ministry of Health Singapore (MOH): https://www.moh.gov.sg/covid-19
- Italy Ministry of Health: http://www.salute.gov.it/nuovocoronavirus
- 1Point3Arces: https://coronavirus.1point3acres.com/en
- WorldoMeters: https://www.worldometers.info/coronavirus/
- COVID Tracking Project: https://covidtracking.com/data. (US Testing and Hospitalization Data. We use the maximum reported value from - - "Currently" and "Cumulative" Hospitalized for our hospitalization number reported for each state.)
- French Government: https://dashboard.covid19.data.gouv.fr/

