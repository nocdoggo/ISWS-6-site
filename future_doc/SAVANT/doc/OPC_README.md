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

| SN   | Date       | Start Time | End Time |
| ---- | ---------- | ---------- | -------- |
| 1    | 09/23/2018 | 22:59:11   | 00:00:42 |
| 2    |            |            |          |
| 3    |            |            |          |
| 4    |            |            |          |

As for ==OPC 2== located at `Lower Convergence Tower`:

| SN   | Date | Start Time | End Time |
| ---- | ---- | ---------- | -------- |
|      |      |            |          |
|      |      |            |          |
|      |      |            |          |



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

`.csv` files 