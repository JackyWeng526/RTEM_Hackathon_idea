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

We have a hotel building and get some observations of its HVAC systems for lobby space. 
(RTEM only supports some metadata with a few relationships between spaces and devices.)

At first, we can take a look at datasets of HVAC systems.

### Chiller water system

*Timeseries data of chilled water temperature. (TCHS: Supply chilled water temperature; TCHR: Return chilled water temperature)*
![TCH_Data](https://github.com/JackyWeng526/RTEM_Hackathon_idea/blob/main/docs/Chilled_Water_Temp_Timeseries.PNG)

*Timeseries data of chilled water flow rate. (QCH: Quantity of chilled water, unit: CMH)*
![QCH_Data](https://github.com/JackyWeng526/RTEM_Hackathon_idea/blob/main/docs/Chilled_Water_FlowRate_Timeseries.PNG)

*Timeseries data of cooling load. (Cooling load of two chillers, unit: USRT)*
![RT_Data](https://github.com/JackyWeng526/RTEM_Hackathon_idea/blob/main/docs/Cooling_Load_Timeseries_v2.PNG)

*Timeseries data of chiller performance. (cooling performance, energy consumption per USRT, unit: KW/RT)*
![KWRT_Data](https://github.com/JackyWeng526/RTEM_Hackathon_idea/blob/main/docs/Chiller_Performance_KWRT_Timeseries.PNG)

### AHU system

*Timeseries data of air temperature. (TAS: Supply air temperature; TAS_SP: Setpoint of supply air temperature, unit: degree C)*
![AHU_5_T_Data](https://github.com/JackyWeng526/RTEM_Hackathon_idea/blob/main/docs/AHU_5_TA_Timeseries.PNG)
![AHU_7_T_Data](https://github.com/JackyWeng526/RTEM_Hackathon_idea/blob/main/docs/AHU_7_TA_Timeseries.PNG)
![AHU_15_T_Data](https://github.com/JackyWeng526/RTEM_Hackathon_idea/blob/main/docs/AHU_15_TA_Timeseries.PNG)

### Indoor air temperature and cooling efficiency

According to AHU datasets, there are sometimes divergences between TAS and TAS_SP in all three AHUs.

It means the chillers may not support the corresponding cooling load for AHUs, making the TAS higher or lower than TAS_SP. (especially AHU_5)

Thus, we try to analyze the AHU datasets with chiller datasets to understand the advancing interaction of the HVAC system.

#### Insight of Chiller dataset

The chiller performance could be displayed through supply chilled water temperature (TCHS), chilled water temperature difference (TCHD), or chilled water follow rate (QCH).

*Advancing analysis of chiller performance. *
![CH_22_3_Data](https://github.com/JackyWeng526/RTEM_Hackathon_idea/blob/main/docs/CH_22_3_RT_KWRT_Analysis.PNG)
![CH_22_4_Data](https://github.com/JackyWeng526/RTEM_Hackathon_idea/blob/main/docs/CH_22_4_RT_KWRT_Analysis.PNG)


