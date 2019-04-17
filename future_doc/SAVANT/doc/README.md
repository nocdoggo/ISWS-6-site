## How to use reader toolkit

### 0. Get Started

Please download the `NetCDF Reader Toolkit` as a whole and ==extract== to whichever you would like it to be.

### 1. Data Requirement

Please create a sub folder with any desired name you would like. Say, in this case, we name it as `data` under the `~\NetCDF Reader Toolkit\`. Then, please download the <kbd>.nc</kbd> files from the ==SAVANT== folder, and save then under `data` folder.



### 2. How To Execute

#### 2.1 How to Run the Toolkit

Fire up the ==MATLAB== and navigate to the `NetCDF Reader Toolkit`, then simply click on `run.m` and then  <kbd>Run</kbd> from the menu bar, or in the ==Command Window== type in 

```matlab
run
```

Then, the program should prompt:

```matlab
=============================================================================
Please enter the name of the input NetCDF file folder: 
```

Simply type in the name of the data folder you created, in this case, we have it as `data`, so type in:

```matlab
data
```

The program will detect how many <kbd>.nc</kbd> files are there in the data directory. Then, simply relax and let the program do the trick. You should see something as:

```matlab
There are 20 NetCDF files in this directory.
```

Next, the program will ask you how would you want your ==Excel== sheets look like. You should be greeted by:

```matlab
How would you like your table to look like? Group by [H]eight or [T]ower?
[H/T]: 
```

Type in <kbd>H</kbd> if you want to ==store all relevant data which share the same height==. Type in <kbd>T</kbd> if you would like to ==store all the relevant data which are at the same tower location==.

Once done, under the `NetCDF Reader Toolkit`, you shall be able to find the converted ==Excel== datasheets depending on your output selection.

If you decide to ==store all relevant data which share the same height==, you should see something like this:

![](C:\Users\wzhang77\Documents\MATLAB\doc\01.JPG)

It will save the exported data with the style of:

```bash
<Date>_<Height>.xlsx
```

Otherwise, if you ==store all the relevant data which are at the same tower location==, you should see something like this instead:

![](C:\Users\wzhang77\Documents\MATLAB\doc\04.JPG)

It will save the exported data with the style of:

```bash
<Date>_<Tower>.xlsx
```

Once all <kbd>.nc</kbd> files have been converted to <kbd>.xslx</kbd> files, the error messages and export log will be same as:

```bash
ExportLog.txt
```

Vola! You are good to go for the next step of your data visualization.

#### 2.2 Output Files

Since the weather station data were collected under the <kbd>UTC</kbd> time-zone. Therefore, for the shear of simplicity, the toolkit has been set to convert the time-zone back to <kbd>CST</kbd> by default.

![](C:\Users\wzhang77\Documents\MATLAB\doc\06.JPG)

As you can see, mostly the Excel file starts at ==19:00 or 20:00== depending the data collection schedule. Therefore, if the file name stated as:

```bash
1007_rel.xlsx
```

The date before the `0:00:00` ==refers to `Oct 06` rather than `Oct 07` due to the time-zone differences.== Please keep that in mind!

### 3. Troubleshooting

Sometimes, the exporting process might not be so smooth. Yet, I have designed the program with the knowledge of missing data or file corruption in mind. So, when encountering problems, the program won’t halt and kick you out from continuing. Instead, it will post error messages in the ==Command Window==. So, please pay attention to it. you might see something like the following:

#### 3.1 Non-existing Data File

![](C:\Users\wzhang77\Documents\MATLAB\doc\03.JPG)

When you encounter this error, this simply means no <kbd>.nc</kbd> files were detected under the data folder you typed in.

So, please check if you **type in the wrong folder name in the program**, or you **did not save the proper data file properly**. Make sure you have the correct <kbd>.nc</kbd> files under the data folder you designed. Then, ==re-run the program==.

#### 3.2 Error While Fetching

![](C:\Users\wzhang77\Documents\MATLAB\doc\02.JPG)

Also, it is always a good idea to check the output log mentioned before. But in the command window, everything is more ease for eyes.

![](C:\Users\wzhang77\Documents\MATLAB\doc\05.JPG)

When you encounter this issue, this simply means the targeted variable was not recorded during the data collection. The variables have been filled up with 0s, in order to void table creation issues. (Nothing you can do about it unless you have a time machine. Then travel back in time and … change the world?)

Should you have any questions? Contact ==SAVANT== staff for more details.