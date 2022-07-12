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

Thus, we try to analyze the AHU data with chiller datasets to understand the advancing interaction of the HVAC system.

#### Insight of Chiller dataset

The chiller performance could be displayed through supply chilled water temperature (TCHS), chilled water temperature difference (TCHD), or chilled water follow rate (QCH).

*Advancing analysis of chiller performance.*
![CH_22_3_Data](https://github.com/JackyWeng526/RTEM_Hackathon_idea/blob/main/docs/CH_22_3_RT_KWRT_Analysis.PNG)
![CH_22_4_Data](https://github.com/JackyWeng526/RTEM_Hackathon_idea/blob/main/docs/CH_22_4_RT_KWRT_Analysis.PNG)

#### Insight of AHU dataset

Unlucky, the AHU data is not sufficient to verify all of our hypotheses. However, we still have some findings.

The TAS difference (TASD) of some AHUs seems to show relvance to [cooling coil valve command (CCVC)] or [chilled water temperature difference (TCHD)].

*Advancing analysis of AHU temperature divergences. (Displayed by CCVC)*
![AHU_CCVC_Data](https://github.com/JackyWeng526/RTEM_Hackathon_idea/blob/main/docs/AHU_AHU_CCVC.PNG)

*Advancing analysis of AHU temperature divergences. (Displayed by TCHD)*
![AHU_TCHD_Data](https://github.com/JackyWeng526/RTEM_Hackathon_idea/blob/main/docs/AHU_TCHD.PNG)

### Human Comfort and HVAC Energy Balance

To talk about Human Comfort and HVAC Energy Balance, we suppose TCHD may be one of the key variables that connect chillers and AHUs operation.

In *Insight of Chiller dataset*, we can find a optimal TCHS range for better chiller performance.

However, the TCHD would influence AHU temperature difference that may impact human thermal comfort.

Therefore, we souhld find a chillers and AHUs operation strategy that satisfies indoor human comfort and energy consrvation.

### Future Work

1. Utilize resources of RTEM datasets to verify hypothese and expand the research scale.
2. Design a multivariable optimizing model for Human Comfort and HVAC Energy Balance.

### Authors
- [@Jacky Weng](https://github.com/JackyWeng526)
- [@Patrick Fu](https://github.com/PatrickFu0302)

### Acknowledgement
The datasets in this repository is from RTEM Hackathon. 
The metadata and other information of the sample buildings are released with consent.
The module here is just the sample, not the real one in the field.





