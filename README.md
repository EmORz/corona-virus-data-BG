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

# Other 
Visual Dashboard (desktop):
https://www.arcgis.com/apps/opsdashboard/index.html#/bda7594740fd40299423467b48e9ecf6

Visual Dashboard (mobile):
http://www.arcgis.com/apps/opsdashboard/index.html#/85320e2ea5424dfaaa75ae62e5c06e61

Lancet Article:
An interactive web-based dashboard to track COVID-19 in real time

Provided by Johns Hopkins University Center for Systems Science and Engineering (JHU CSSE):
https://systems.jhu.edu/
