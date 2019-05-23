# OPC/OPS Dataset Readme

## 1. Dataset Title

The RAW datasets being retrieved from the machine have been initially converted to `.csv` files. 

When it comes to the naming regime, the files are stored under `~/OPC`, categorized based on date `MMDDYYYY`. 



## 2. Dataset Authors

| Name:   | Dr. Junming Wang     | Dr. David Kristovich | Dr. April Hiscox      |
| :------ | -------------------- | -------------------- | --------------------- |
| Role:   | Lead Auther          | Corresponding Author | Corresponding Author  |
| E-mail: | wangjim@illinois.edu | dkristo@illinois.edu | hiscox@mailbox.sc.edu |
| Phone:  | (217)-300-2529       | (217)-333-7399       | (803)-777-6604        |



## 3. Time of Interest

As for ==OPC 1== located at `Release Tower`:

| SN   | Date       | Start Time | End Time              |
| ---- | ---------- | ---------- | --------------------- |
| 1    | 09/23/2018 |            |                       |
| 2    | 10/11/2018 | 21:11:09   | 23:59:59              |
| 3    | 10/12/2018 | 00:00:00   | 07:05:03              |
| 4    | 10/16/2018 | 01:58:19   | 06:31:18              |
| 5    | 10/23/2018 | 22:33:05   | 06:53:05<sup>+1</sup> |
| 6    | 10/27/2018 | 19:03:19   | 00:22:43<sup>+1</sup> |
| 7    | 10/29/2018 | 18:05:38   | 01:11:41<sup>+1</sup> |
| 8    | 11/02/2018 | 17:11:15   | 07:18:23<sup>+1</sup> |
| 9    | 11/07/2018 | 21:11:09   | 23:01:27              |
| 10   | 11/10/2018 | 18:04:14   | 20:34:12              |
| 11   | 11/11/2018 | 19:23:59   | 01:15:01<sup>+1</sup> |
| 12   | 11/13/2018 | 23:30:44   | 07:50:44<sup>+1</sup> |

As for ==OPC 2== located at `Lower Convergence Tower`:

| SN   | Date       | Start Time | End Time              |
| ---- | ---------- | ---------- | --------------------- |
| 1    | 09/23/2018 | 22:59:11   | 00:00:42<sup>+1</sup> |
| 2    | 10/11/2018 | 23:44:58   | 23:59:59              |
| 3    | 10/12/2018 | 00:00:00   | 07:05:03              |
| 4    | 10/16/2018 | 01:58:19   | 06:31:18              |
| 5    | 10/23/2018 | 22:23:48   | 06:43:48<sup>+1</sup> |
| 6    | 10/27/2018 | 19:14:27   | 00:02:05<sup>+1</sup> |
| 7    | 10/29/2018 | 17:59:04   | 01:05:41<sup>+1</sup> |
| 8    | 11/02/2018 | 18:04:02   | 07:46:18<sup>+1</sup> |
| 9    | 11/07/2018 | 20:54:00   | 23:08:33              |
| 10   | 11/10/2018 | 17:32:37   | 20:12:01              |
| 11   | 11/11/2018 | 19:29:38   | 01:15:08<sup>+1</sup> |
| 12   | 11/13/2018 | 00:18:21   | 08:01:27              |

Notice that `+1` refers to the fact the time is on the next day of the experiment `Date`. 



## 4. Area of Interest

The experiments were conducted at the test field located at `Crowley Rd Mahomet Township, IL 61853`.

![OPC Device Location](C:\Users\wzhang77\Documents\GitHub\ISWS-6-site\future_doc\SAVANT\doc\OPS_Location.png)

As shown in the picture above, there are 4 towers being constructed in the test field. The `OPC #1` was installed at `Release Tower` with a height of `3 meters`, and `OPC #2` was installed at `Lower Convergence Tower` with a height of `3 meters`. 

#### 4.1 Device Setup Profile

| Tower             | Longtitude    | Latitude      | Device          |
| ----------------- | ------------- | ------------- | --------------- |
| Initiation        | 40°12'41.46"N | 88°24'37.99"W |                 |
| Release           | 40°12'42.04"N | 88°24'25.52"W | ==OPC #1 @ 3M== |
| Upper Convergence | 40°12'39.78"N | 88°24'19.61"W |                 |
| Lower Convergence | 40°12'36.91"N | 88°24'13.26"W | ==OPC #2 @ 3M== |



## 5. Data frequency

| Time Zone | Log Interval      | Type       |
| --------- | ----------------- | ---------- |
| UTC       | 0:00:01 [H:MM:SS] | Continuous |



## 6. Data Spatial Type

The datasets have been converted to `.csv` and `.bin` file. 

#### 6.1 BIN File

`.bin` files include the device and firmware status, information, and maintenance record. File stored in ASCII encoding method.

#### 6.2 CSV File

`.csv` files include the experimental data, measuring methods, and plotting information. File stored in `comma-separated value` tabular form.



## 7. General Dataset Description

The device we are using is Optical Particle Sizer 3330 from TSI. Device information can be found at:

<https://www.tsi.com/optical-particle-sizer-3330/>

For the measurement, the device separates the molecule counts based on the size of the particle. At the beginning of each data file, you can find out that the machine categorizes particles into 17 bin groups.

| Bin                    | Size  |
| ---------------------- | ----- |
| Bin 1 Cut Point   (um) | 0.3   |
| Bin 2 Cut Point (um)   | 0.374 |
| Bin 3 Cut Point (um)   | 0.465 |
| Bin 4 Cut Point (um)   | 0.579 |
| Bin 5 Cut Point (um)   | 0.721 |
| Bin 6 Cut Point (um)   | 0.897 |
| Bin 7 Cut Point (um)   | 1.117 |
| Bin 8 Cut Point (um)   | 1.391 |
| Bin 9 Cut Point (um)   | 1.732 |
| Bin 10 Cut Point (um)  | 2.156 |
| Bin 11 Cut Point (um)  | 2.685 |
| Bin 12 Cut Point (um)  | 3.343 |
| Bin 13 Cut Point (um)  | 4.162 |
| Bin 14 Cut Point (um)  | 5.182 |
| Bin 15 Cut Point (um)  | 6.451 |
| Bin 16 Cut Point (um)  | 8.031 |
| Bin 17 Cut Point (um)  | 10    |

The data was collected with a time interval of `1 second` as mentioned previously. And `Test Start Time` and `Test Start Date` are also included in the dataset. The data points were indexed based on second apart from the `Test Start Time`.



## 8. File Names

The data files are named under the regime of:

```bash
YYYY_MM_DD-HH_MM_SS-TEST_00<OPCID>.csv
```

For example, the data collected from `OPC#1` on October 23, starting at `22:33:05`, will have a file name of `2018_10_23-22_33_05-TEST_001.csv`.



## 9. Data Restrictions

Datasets collected from OPC devices are subject to restrictions which applies to `SAVANT` Project.



## 10. Digital Object Identifier (DOI)

NCAR/EOL are in charge of DOI management of the datasets.



## 11. GCMD Keywords

```java
Category: EARTH SCIENCE SERVICES

Topic: ENVIRONMENTAL ADVISORIES

Term: WEATHER/CLIMATE ADVISORIES

Variable_Level_1: DUST/ASH ADVISORIES

UUID: 8f7c2388-24e4-4f90-a833-6dc166693879
```

