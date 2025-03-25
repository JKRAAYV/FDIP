# FDIP

## Overview
___
### Flight Data Insight Pipeline

**Description**
The aim of this project is gather flight insights, preferably live/api insights, processess the data in a pipeline utilizing cloud infrastructure, and produce insights from the data.

**Project Requirements**
While a Trello Kanban will be utilized personally, progress will be tracked below and updated as primary tasks are completed. ☐ | ☑

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
| ☐  | Flask Web App | Not started yet. |

### Current State

Currently functioning pipeline.