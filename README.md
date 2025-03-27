# FDIP

## Overview

### Flight Data Insight Pipeline
**Description**
The aim of this project is gather flight insights, preferably live/api insights, processess the data in a pipeline utilizing cloud infrastructure, and produce insights from the data.

**Project Management**
The project will be done in 1 weel sprints whenever new ideas or features are acquired. Primary requirements that aren't completed in sprint time will roll over to the next sprint period, secondary requirements that aren't completed will be placed in the backlog. While a Trello Kanban will be utilized personally, progress will be tracked below and updated as primary tasks are completed. ☐ | ☑ 
___
## Backlog
Ideas or secondary requirements that weren't completed, will be placed here.

| Requirement | Description | Origin |
| ------------- | ------------- | ------------- |
| Flask Web App | A flask web app for fullstack testing. | Secondary requirement of v0.0001 |
| Website | A node.js website hosting querying and interactive map. | Idea |

___
## Version Updates

#### v0.0001

**Description**
Set up the intial architecture for a functioning pipeline, and possibly connect the insights to a dashboard or web app.

**Initial Project Requirements**

Completed all but one of the requirements for the initial project requirements.

| Completed  | Primary Requirement | Description |
| ------------- | ------------- | ------------- |
| ☑  | Choose data source. | Utilizes OpenSky API for live flight data and tgftp.nws.noaa.gov for airport weather data (very limmited integration) |
| ☑  | Choose cloud provider. | Azure Blob storage.
| ☑  | Get flight information data and test local PySpark transformations. | Initially, I tested the apis, and created the static files in the two notebooks stored under NotebookApiAnalysis, I also used this to understand how I might transform the data, and for planning the pipeline.|
| ☑  | Set up cloud storage. |  Blob storage with two directories, one storing the static airport data and airports with icao data, and one storing processed data, flight, processed airports including weather, and airports with weather csv.|
| ☑  | Upload raw data. | Uploaded the two files created locally in the analysis notebooks.|
| ☑  | Build transformation script to run in cloud. | Built an official pipeline stored under NotebookOfficial pipeline, removing sensitive info with comments until I set up environment variables. (Not really needed since the production file is stored in databricks anyway)|
| ☑  | Set up automation. | Created a databricks pipeline on a schedule for every 6 hours to update the data. (Could do more frequently, but currently for budgeting purposes set lower.)|
| ☑  | Save processed output. | Successfully transform and process the data stored within blob processed folder, overwrites existing data with latest data. (Doesnt store historical data)|


| Completed  | Secondary Requirements | Description |
| ------------- | ------------- | ------------- |
| ☑  | Power BI Dashboard | Successfuly implemented the processed data utilizing a connector for blob storage. Still in development.|
| ☐  | Flask Web App | Placed in Backlog at time of sprint. |

**Period:** 3/21/2024 - 3/23/2024

**Final comments:** Was able to complete all the primary requirements, and one secondary requirement. Some issues persist with the weather data for airports. With the small weather coverage, I may consider opting out of weather data. In the next sprint I would like a to add a more comprehensive description on aircraft, possibly find an API or database that contains aircraft by their icao24 code.
___
#### v0.0002

**Description:** Integrate more comprehensive description of flights by utilizing database to grab the aircraft's descriptive data paired with their flight data. Possibly remove weather data integration.

**Requirements**

| Completed  | Primary Requirement | Description |
| ------------- | ------------- | ------------- |
| ☑  | Find Aircraft Data based on icao24 code. | Found a directory utilizing the same api for flight data the provides a huge comprehensive list of aircraft data in one large file, seems to be updated periodically. |
| ☐  | Update pipeline to include aircraft data. |  |

| Completed  | Secondary Requirements | Description |
| ------------- | ------------- | ------------- |
| ☐  | Update BI Dashboard | |
| ☐  |Remove weather data pipeline functionality due to low coverage. | |

**Period:** 3/27/2024 -

**Final comments:** N/A