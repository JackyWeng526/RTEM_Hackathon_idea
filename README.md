# RTEM_Hackathon_idea

## Open Source Building Datasets

In 2022, there is a Hackathon competition about building and energy held by [RTEM](https://www.rtemhackathon.com/).

During the competition, we can have approximately 200 buildings worth of time-series data from the RTEM database. 

The provided building meta data is shown as following: 

![Building_Device_Meta](https://github.com/JackyWeng526/RTEM_Hackathon_idea/blob/main/docs/Building_Device_Meta.PNG)

To inspect building data of certain building:

![Building_Device_Meta](https://github.com/JackyWeng526/RTEM_Hackathon_idea/blob/main/docs/Building_DataFrame.PNG)


## HVAC performance and Human Comfort - Case Study

We intend to investigate the interactions between chiller plants and AHUs and further discuss the optimal strategy for balancing indoor human comfort and energy conservation of HVAC system.

At first, we can take a look at HVAC system data.

*Timeseries data of chilled water temperature. (TCHS: Supply chilled water temperature; TCHR: Return chilled water temperature)*
![TCH_Data](https://github.com/JackyWeng526/RTEM_Hackathon_idea/blob/main/docs/Chilled_Water_Temp_Timeseries.PNG)

*Timeseries data of chilled water flow rate. (QCH: Quantity of chilled water, unit: CMH)*
![QCH_Data](https://github.com/JackyWeng526/RTEM_Hackathon_idea/blob/main/docs/Chilled_Water_FlowRate_Timeseries.PNG)

*Timeseries data of cooling load. (Cooling load of two chillers, unit: USRT)*
![RT_Data](https://github.com/JackyWeng526/RTEM_Hackathon_idea/blob/main/docs/Cooling_Load_Timeseries_v2.PNG)

*Timeseries data of chiller performance. (cooling performance, energy consumption per USRT, unit: KW/RT)*
![KWRT_Data](https://github.com/JackyWeng526/RTEM_Hackathon_idea/blob/main/docs/Chiller_Performance_KWRT_Timeseries.PNG)
