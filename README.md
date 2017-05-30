# xanthos
Xanthos is a Python package designed to quantify and analyse global water availability historically and in the future at 0.5° × 0.5° spatial resolution and a monthly time step.  Its performance and functionality was tested through real-world applications. It is open-source, extensible and accessible for researchers who work on long-term climate data for studies of global water supply, and the Global Change Assessment Model (GCAM). This package integrates inherent global gridded data maps, I/O modules, hydrologic processes and diagnostics modules parameterized by a user-defined configuration file.

# introduction
Xanthos is a code package for calculating global water availability, developed at the Joint Global Change Research Institute of the Pacific Northwest National laboratory, USA. The initial objective of this model is to quantify changes in future freshwater availability under various climate change regimes, and to serve as the freshwater supply component of the Global Change Assessment Model (GCAM) [1-3]. The model has been used in previous publications to explore different climate and socioeconomic scenarios over the 21st century and assess their implications on water scarcity regionally and globally [4-5].

The core algorithm of Xanthos is the hydrology model, which includes modules for calculating potential evapotranspiration (PET), runoff generation, and stream routing – shown in Figure 1. The underlying equations and algorithms for the hydrology model were described in details in Hejazi et al [4], and Zhou et al. [6]. The model requires gridded monthly temperature and precipitation, a maximum soil water storage capacity map (assumed static over time in this study) and calculates gridded monthly runoff, PET, actual evapotranspiration, water storage in the soil column, channel water storage and average channel flow. The PET module uses the Hargreaves method [5], and requires monthly temperature data (average temperature and average daily temperature range in Celsius). The stream routing module includes a cell-to-cell river routing scheme adopted from the modified river transport model (RTM), which uses a linear advection formula [6]. The aggregation module of Xanthos provides estimates of maximum naturally-available water fluxes (mm) or volumes (billion m3) monthly or annually (i.e., total monthly runoff) for each river basin. Xanthos also offers the user an option to obtain the annual volumes (billion m3/year) of renewable water resources that are accessible for human use in each basin [7], which is calculated by the accessible-water module.

Xanthos was designed for independent applications and it can also serve as the water supply component in GCAM. The primary goals are as follows:
1.	Be distributed as an open-source package that can be utilized and extended by researchers who study global hydrology
2.	Estimate gridded (0.5 degree resolution) monthly global results of runoff, average channel flow, actual evapotranspiration, and water storage in the soil column
3.	Employ a standardized configuration and simplified input structure that is easy for the user to update
4.	Direct diagnostics on the runoff results.

To achieve the above goals, Python was selected as the programming language because of its easy-to-use and easy-to-install-with-libraries and it flexibility.

![alt-text](https://github.com/JGCRI/xanthos/blob/master/docs/workflow.png)