# Possible Drainage Flow Criteria

This documentation aims to provide a simple rundown on how we comprehend the raw data being collected from the SAVANT project during the 1^st^ stage.

## 0. Getting Started

All the raw datasets can be found under the `SAVANT` shared folder stored on [Box](https://www.box.com). The datasets which we are focusing on are:

- Dusttrack 8520/8530
- OPC 3310
- Wind and temperature sensor data

## 1. Pre-processing

### 1.1 Datasets Formatting

As for Dusttrack 8520/8530 datasets, they were stored in `.csv` format which has proper time stamps in the file. No further action required.

As for wind and temperature sensor datasets, they were initially stored in `.nc` file format. For the convenience of data visualization, we convert them into `.xslx` format with time converted accordingly based on the time zone. For more information, please visit the ==NCToolkit Manual==. 

### 1.2 Requirements

- [ ] Check if the time has been converted properly, with the reference to the website April provided.
- [ ] Check the daily data collection notes in the Dusttrack raw data folder to see if there is any miss calibration to the device time.

## 2. Drainage Finding

During the 1^st^ stage, we are trying to identify the possible drainage flow time range based on the following criteria. 

### 2.1 Dusttrack

As for Dusttrack datasets, we label out the possible drainage time period by:

1. Find out all time stamps where the particle concentration is `>= 0.1`
2. The peak is not only 1 time for an extreme short period of time.

### 2.2 Wind Speed

For the wind speed profiles, we use the wind speed at `10m` as the reference speed.

1. Check the wind speed at `0.2m`, `1.5m`, `4.5m`, and `6m`.
2. Make sure ==V<sub>0.2m</sub> >  V<sub>10m</sub>, V<sub>1.5m</sub> >  V<sub>10m</sub> , V<sub>4.5m</sub> >  V<sub>10m</sub>, V<sub>6.0m</sub> >  V<sub>10m</sub>==. 
3. Also, the trend should be ==V<sub>0.2m</sub> >  V<sub>1.5m</sub> > V<sub>4.5m</sub> >  V<sub>6.0m</sub>==.

### 2.3 Wind Direction

For the wind direction profiles, based on the gully, we follow the following criteria.

1. Check the direction angle as: ==70 <= Θ<sub>1.5m</sub>, Θ<sub>4.5m</sub> <= 320==.
2. (Optional) Check if the direction angle at higher space, say Θ<sub>6.0m</sub> and Θ<sub>10m</sub>  are different than Θ<sub>1.5m</sub> and Θ<sub>4.5m</sub>. Θ<sub>0.2m</sub> is ignored due to the existence of a plethora of varies objects. 

### 2.4 Temperature (Optional)

For the temperature profile, we need to see if they follow the following criteria.

1. ==T<sub>0.2m</sub> < T<sub>1.5m</sub> < T<sub>4.5m</sub> < T<sub>6.0m</sub>==.

## 3. Decision Making

Once we successfully process all the datasets, we can layout the possible drainage time periods which yield from each dataset, and see if they share anything in common. Highlight and extract drainage flow period datasets for 2^nd^ stage processing.

