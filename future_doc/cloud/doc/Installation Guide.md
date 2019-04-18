# Installation Guide

It is glad to know that you want to set up the toolkit on your local workbench. Yet, it is currently not available in a simple executable package since the toolkit has not walked out from its alpha period. But do stay tuned, since I have created some automatic scripts to make your installation process easier. Also, we plan to have our first beta release soon! So make sure too smash the `Watch`  and `Star` icons on the top right of the page!

## 0. Prerequisites 

In this section, we will talk about the hardware, system, and software requirements

### 0.1 Hardware

| Component Name        | Recommended Set-up                | Minimum Requirement                |
| --------------------- | --------------------------------- | ---------------------------------- |
| CPU                   | Intel i-series/AMD Ryzen 4+ Cores | Intel i-series/AMD Ryzen 2 Cores   |
| RAM                   | 2 GB or more                      | 256 MB                             |
| GPU                   | ==NVidia== with ==CUDA==          | As long as you see stuff on screen |
| Pre-install Free Disk | 5 GB or more                      | 582 MB                             |

If your system does have NVidia graphic card, and would like to utilize the GPU hardware acceleration. Please visit [CUDA Zone](https://developer.nvidia.com/cuda-zone) to obtain the latest package for yourself prior to the installation process.

### 0.2 System Environment

| System Type         | Recommended                             | Minimum Requirement                        |
| ------------------- | --------------------------------------- | ------------------------------------------ |
| Windows             | Windows 10/Server 2016 R2 (64-bit)      | Windows 7 (32-bit)/Server 2008 R2 (32-bit) |
| MacOS               | 10.14+                                  | 10.8.3                                     |
| Debian/Ubuntu/Libux | 4.10 Generic Kernel+/18.04 LTS (64-bit) | 2.6.10 Generic/12.04 LTS (32-bit)          |

Please try to update your system beyond anything released in 2010 to prevent dependency related issue. Plus, CUDA and OpenCV hit hard performance roadblock in elder system build.

More specifically, if you are on Server Edition system, particularly if you are on Server 2008, you should make sure you have the system administrator permission to add extra DLL files into system folders.

### 0.3 Software

In order to run our toolkit, you need to install the following softwares:

- [Python 3.3+](<https://www.python.org/downloads/>)

- [Java 8+](<https://www.oracle.com/technetwork/java/javase/downloads/index.html>) (Java 7 works but not recommended!)

- [NOAA Weather and Climate Toolkit](<https://www.ncdc.noaa.gov/wct/>)

- [CUDA](<https://developer.nvidia.com/cuda-zone>) ==Optional==

- C Library Dependency `System-oriented` ==See in later section==

- [MATLAB R2015+](<https://www.mathworks.com/products/matlab.html>) `If you wish to run on older system build `

  

  For `Java 7`, since it is out of its support period, Oracle has issued mandatory update and [migration guide](<https://www.oracle.com/technetwork/java/javase/jdk8-adoption-guide-2157601.html>) to most users. All machines which are able to install `Java 7` are guaranteed to support the version 8. Hilariously, `Java 8` has a higher performance rate than `Java 7`, almost in every single way. A sample benchmark can be found [here](<https://engineering.indeedblog.com/blog/2016/09/job-search-web-app-java-8-migration/>). If you still insist from updating your Java SE, please re-consider your career choice.

  For folks running on the edge of the world, if you are on `Java 11`, since API calls are being drastically changed, please submit tickets if anything does not work for you.

  

If you are on older version of system, we do suggest you to update your system. As the dependency libraries either won’t compile or execute for your old system build. But we did not forget about you old school folks. There is also a MATLAB build available with the similar functionality available. Yet, the maintenance and feature update would be 2 to 4 weeks delayed since this is a one-man army work. Please have mercy on me!

​	If you are on edition prior to `MATLAB R2015a`, please make sure to comment out the spectrum related codes.

#### 0.3.1 Windows

##### 0.3.1.1 C/C++ Compiler Environment

The C/C++ compiler environment is needed for `OpenCV` feature to work properly. You do NOT need to download and install directly from `OpenCV` website, since large portion of the features won’t be needed unless you plan to use `CUDA` acceleration. `OpenCV`is used in the frame extraction process and parallel processing.

For folks running on Windows, please make sure to follow the following checklist to redirect to the specific links in order to obtain all the required system packages.

- [ ] [Visual C++ Redistributable for Visual Studio 2012 Update 4](<https://www.microsoft.com/en-us/download/details.aspx?id=30679>)
- [ ] [Visual C++ Redistributable Packages for Visual Studio 2013](<https://www.microsoft.com/en-us/download/details.aspx?id=40784>)
- [ ] [Visual C++ Redistributable for Visual Studio 2015](<https://www.microsoft.com/en-us/download/details.aspx?id=48145>)
- [ ] [Visual C++ Redistributable for Visual Studio 2017](<https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads>)

Before installing or downloading any of those, please navigate to the `Programs and Features` to find out which C++ Redistributable you have already installed.

For users on system prior to ==Windows 8== and ==Windows Server 2012==:

1. Click **Start** ![img](https://support.hp.com/doc-images/358/c00850235.gif), and then click **Control Panel**.

2. Under **Programs**, click **Uninstall a program**. The **Uninstall or change a program** window opens. You should be able to find all the software you installed. You may find all the installed Visual C++ Redistributable packages.

   ![Uninstall or change a program](https://support.hp.com/doc-images/923/c01860850.gif)

For users on system same or newer than ==Windows 8== and ==Windows Server 2012==:

1. In Windows, search for and open **Control Panel**. 

   ![img](https://www.howtogeek.com/wp-content/uploads/2018/01/ximg_5a4d2246d7723.png.pagespeed.gp+jp+jw+pj+ws+js+rj+rp+rw+ri+cp+md.ic.GcnMRenyUI.png)

2. In Control Panel, locate **Programs**, then click **Uninstall a program**.

   ![Uninstalling a program](https://support.hp.com/doc-images/602/c05810501.jpg)

3. In the **Uninstall or change a program** window, you should be able to find all the software you installed. You may find all the installed Visual C++ Redistributable packages.

   ![img](https://www.howtogeek.com/wp-content/uploads/2018/01/ximg_5a4d2202e99b6.png.pagespeed.gp+jp+jw+pj+ws+js+rj+rp+rw+ri+cp+md.ic.r7U6AjgjZk.png)

##### 0.3.1.1 Server Edition Extra

As mentioned before, the Server Edition suffers from missing dependency libraries. Please make sure you follow the steps to perform troubleshooting.

> может быть, это немного запоздало, но у нас была такая же проблема, и мы не нашли ответа через Интернет, так что это может помочь кому-то в будущем.
>
> Проблема связана с отсутствующей dll в Window 2008 Server, мы решаем ее копирование этой DLL "msvcp100.dll" в нашей папке% JAVA%/jre7/bin
>
> Надеюсь, что эта помощь
>
> ​																				 ——————————— [QA.RU](<http://qaru.site/questions/7197391/jboss-under-win-server-2008-with-opencv-242>)

When you have missing `msvcp100.dll`, please make sure to install [Visual C++ 2008 Redistributable Package](<https://www.microsoft.com/en-us/download/details.aspx?id=29>). 

When it comes to the ==missing jniopencv_core.dll==, please make sure the `Java` installation was done properly.

##### 0.3.1.2 Python 3

NVIDIATo install Python 3.3 or later, go to the [Python home page](https://www.python.org/) or follow the list in previous section, and download the latest version of Python 3 for your operating system.

==If you have Python 2.7 installed, you do not need to remove it.==

During the installation process, if there is a check-box to add Python 3.X to your path, make sure it is checked before proceeding with the installation.

![img](https://github.com/MrYsLab/s2aio/raw/master/images/pythonInstall.png)

##### 0.3.1.3 Java

Java is a dependency for ==OpenCV==, ==NOAA’s Weather Toolkit== and ==MATLAB== builds.

- Go and obtain the [desired Java SE](<https://www.oracle.com/technetwork/java/javase/downloads/index.html>)

- Under **Java SE Downloads**, click on [![Download JDK](https://www.oracle.com/us/assets/blue-download-sprite-1612430.png)](https://www.oracle.com/technetwork/java/javase/downloads/jdk11-downloads-5066655.html) next to the edition you desired

- Click to accept the license agreement

- Download the windows `.exe` for your operating system (32 bit or 64 bit)

- Use the `.exe` to install

  ![JDK 8 Installation Screen](http://www.herongyang.com/Java/JDK-8-Installation-Screen.jpg)

##### 0.3.1.4 NOAA’s Weather and Climate Toolkit

You may find the latest edition via [NOAA website](<https://www.ncdc.noaa.gov/wct/>). Also, please make sure ==Java== is properly installed. You may find more information about it via its [requirements page](<https://www.ncdc.noaa.gov/wct/requirements.php>).

##### 0.3.1.5 CUDA ==Optional==

THIS IS OPTIONAL, YOU DO NOT NEED THIS IF YOU DO NOT HAVE A DEDICATED NVIDIA GRAPHIC CARD UNIT, OR YOU DO NOT NEED PARALLEL PROCESSING WORK.

IF YOU ARE ONLY INTERESTED IN THE IMAGE SUPER-RESOLUTION, DO NOT HAVE THE HARDWARE OR YOU DO NOT WANT TO GO THROUGH THE HELL OF INSTALLATION, PLEASE CHECK OUT THE OTHER REPO I HAVE FOR A PRE-COMPILED RELEASE VERSION OF IMAGE SUPER-RESOLUTION.

First, download ==CUDA== from the [NVidia website](https://developer.nvidia.com/cuda-90-download-archive)

Select the proper target platform:

[![img](https://github.com/philferriere/dlwin/raw/master/img/cuda-9.0.176-setup1-2018-06.png)](https://github.com/philferriere/dlwin/blob/master/img/cuda-9.0.176-setup1-2018-06.png)

Download all the installers:

[![img](https://github.com/philferriere/dlwin/raw/master/img/cuda-9.0.176-setup2-2018-06.png)](https://github.com/philferriere/dlwin/blob/master/img/cuda-9.0.176-setup2-2018-06.png)

Run the downloaded installers one after the other. Install the files in `A:\whatever\cuda-x.x.xxx`:

[![img](https://github.com/philferriere/dlwin/raw/master/img/cuda-9.0.176-setup3-2018-06.png)](https://github.com/philferriere/dlwin/blob/master/img/cuda-9.0.176-setup3-2018-06.png)

[![img](https://github.com/philferriere/dlwin/raw/master/img/cuda-9.0.176-setup4-2018-06.png)](https://github.com/philferriere/dlwin/blob/master/img/cuda-9.0.176-setup4-2018-06.png)

[![img](https://github.com/philferriere/dlwin/raw/master/img/cuda-9.0.176-setup5-2018-06.png)](https://github.com/philferriere/dlwin/blob/master/img/cuda-9.0.176-setup5-2018-06.png)

[![img](https://github.com/philferriere/dlwin/raw/master/img/cuda-9.0.176-setup6-2018-06.png)](https://github.com/philferriere/dlwin/blob/master/img/cuda-9.0.176-setup6-2018-06.png)

After completion, the installer should have created a system environment (sysenv) variable named `CUDA_PATH` and added `%CUDA_PATH%\bin` as well as`%CUDA_PATH%\libnvvp` to `PATH`. Check that it is indeed the case. If, for some reason, the CUDA env vars are missing, then:

1. Define a system environment (sysenv) variable named `CUDA_PATH` with the value `A:\whatever\cuda-x.x.xxx`
2. Add`%CUDA_PATH%\bin` and `%CUDA_PATH%\libnvvp` to `PATH`

When it comes to cuDNN, per NVidia's [website](https://developer.nvidia.com/cudnn), "cuDNN provides highly tuned implementations for standard routines such as forward and backward convolution, pooling, normalization, and activation layers," hallmarks of convolution network architectures. Download cuDNN from [here](https://developer.nvidia.com/rdp/cudnn-download). Choose the cuDNN Library for Windows that matches the ==CUDA== version:

NVIDIA has recently removed the option for the 7.0.4 Windows download. If your system can not support the latest edition, or you are on the NVIDIA 300 to 400 series, you can download it [here](https://developer.nvidia.com/compute/machine-learning/cudnn/secure/v7.0.4/prod/9.0_20171031/cudnn-9.0-windows10-x64-v7).

[![img](https://github.com/philferriere/dlwin/raw/master/img/cudnn-7.0.4-for-cuda-9.0-setup1-2018-06.png)](https://github.com/philferriere/dlwin/blob/master/img/cudnn-7.0.4-for-cuda-9.0-setup1-2018-06.png)

The downloaded ZIP file contains three directories (`bin`, `include`, `lib`). Extract and copy their content to the identically-named `bin`, `include` and `lib` directories in`%CUDA_PATH%`.

#### 0.3.2 MacOS

##### 0.3.2.1 C/C++ Environment

Please directly install Xcode Command Line Tools. This is released by Apple, so do make sure you have logged into an Apple ID. If you previously installed the full Xcode package, you will need to update Xcode to the newest version (Xcode 8 or newer). After updating Xcode, launch and run the Xcode application and accept the Apple license terms.

You don’t need the full Xcode package to get the Xcode Command Line Tools. You only need the full Xcode package if you are doing development of applications for the Apple operating systems. However, you may have previously installed the full Xcode package.

Check if the full Xcode package is already installed:

```bash
xcode-select -p
```

If you see:

```bash
/Applications/Xcode.app/Contents/Developer
```

the full Xcode package is already installed.

You will need to update Xcode to the newest version (Xcode 8 or newer). Go to the App Store application and check “Updates.” After updating Xcode, be sure to launch the Xcode application and accept the Apple license terms.

If not, you may install it by running:

```bash
gcc
```

You’ll see an alert box:

![alert Xcode Command Line Tools is required](http://railsapps.github.io/images/installing-mavericks-popup.png)

Alternatively, you can use a command to install Xcode Command Line Tools. It will produce a similar alert box. Note the double hyphen:

```bash
xcode-select --install
```

Click “Install” to download and install Xcode Command Line Tools.

The instructions in the alert box are confusing. You don’t need to "Get Xcode" from the App Store. Just click "Install" for the Xcode Command Line Tools. If you have a slow Internet connection, it may take many minutes.

If the download takes a very long time (over an hour) or fails, you can try an alternative. Go to [here](<https://developer.apple.com/downloads/more>) and enter your Apple ID and password. You'll be asked to agree to the terms of the Apple Developer Program. You'll see a list of software packages you can download. Look for the latest version of *Command Line Tools* and click to download the *.dmg* file. Downloading the *.dmg* file is much faster than waiting for the command-line-based download. Install the *.dmg* file by clicking on the package icon.

![downloading Xcode Command Line Tools](http://railsapps.github.io/images/installing-mavericks-download.png)

![installed Xcode Command Line Tools](http://railsapps.github.io/images/imstalling-mavericks-installed.png)

Verify that you’ve successfully installed Xcode Command Line Tools:

```bash
xcode-select -p
/Library/Developer/CommandLineTools
```

Just to be certain, verify that `gcc` is installed:

```bash
gcc --version

Configured with: --prefix=/Library/Developer/CommandLineTools/usr --with-gxx-include-dir=/usr/include/c++/4.2.1
Apple LLVM version 6.0 (clang-600.0.54) (based on LLVM 3.5svn)
Target: x86_64-apple-darwin14.0.0
Thread model: posix
```

On earlier versions of MacOS, it was more difficult to install Xcode Command Line Tools. It required a huge download of the full Xcode package from the Mac App Store or registration as an Apple developer for a smaller Command Line Tools package. Mac OS X Mavericks made installation of Xcode Command Line Tools much simpler.

##### 0.3.2.2 Java

- Java is a dependency for ==OpenCV==, ==NOAA’s Weather Toolkit== and ==MATLAB== builds.
- Go and obtain the [desired Java SE](<https://www.oracle.com/technetwork/java/javase/downloads/index.html>)
- Under **Java SE Downloads**, click on [![Download JDK](https://www.oracle.com/us/assets/blue-download-sprite-1612430.png)](https://www.oracle.com/technetwork/java/javase/downloads/jdk11-downloads-5066655.html) next to the edition you desired
- Click to accept the license agreement
- Download the mac `.dmg`
- Use the `.dmg` to install

![Installing Java SE Development Kit from Oracle](https://introcs.cs.princeton.edu/java/mac/oracle-java8-osx.png)

##### 0.3.2.3 Python 3

The following instructions will guide you through the process of:

- Installing Python 3 using [Homebrew](https://brew.sh/)
- Running multiple Python versions as sand-boxed environments

Open Terminal.app (~/Applications/Utilities) and type 

```bash
python --version
```

If you execute this command in MacOS 10.12 for example, the returned output will read:

> Python 2.7.10

If you execute 

```bash
which python
```

via the command line, it will return the location of the program file, in this case:

> /usr/bin/python

Now we should add Python 3.x via `Homebrew`.

Assuming you have `Homebrew` installed, in ==Terminal.app== execute the following command to install Python 3 : 

```bash
brew install python3
```

 After installation, run the

```bash
python3 --version
```

 command to verify the exact version:

> Python 3.6.4

Now run

```bash
which python3
```

to determine the path where `Homebrew` installed the program file:

> /usr/local/bin/python3

At this stage we have two different version of Python available, yet both version are invoked differently :

- to run a script with **Python 2**, eg. `python test.py`
- to run a script with **Python 3**, eg. `python3 test.py`

##### 0.3.2.4 NOAA’s Weather and Climate Toolkit

You may find the latest edition via [NOAA website](<https://www.ncdc.noaa.gov/wct/>). Also, please make sure ==Java== is properly installed. You may find more information about it via its [requirements page](<https://www.ncdc.noaa.gov/wct/requirements.php>).

##### 0.3.2.5 CUDA ==Optional==

1. Apple has not release any official product with NVidia components for over half a decade. The best bet for you even if you have an old 650M chip is to NOT use it since it has no meaningful acceleration effect. Nor, it has enough streaming processors and shared memory for data bridge. Hence, no.

2. If you are on Hackintosh, and managed to boot in with NVidia GPU. The chance is where when you install the CUDA driver, your Web driver will be replaced and your bootflag can’t be fixed. Hence, it will result in black screen as kernel panic after boot into Unibeast/Clover EFI partition loader. So, no.

3. If you are using a external GPU, you may download the latest package via [CUDA Zone](<https://developer.nvidia.com/cuda-zone>).

Use the following procedure to successfully install the CUDA driver and the CUDA toolkit. The CUDA driver and the CUDA toolkit must be installed for CUDA to function. If you have not installed a stand-alone driver, install the driver provided with the CUDA Toolkit.

Choose which packages you wish to install. The packages are:

- **CUDA Driver**: This will install `/Library/Frameworks/CUDA.framework` and the UNIX-compatibility stub ``/usr/local/cuda/lib/libcuda.dylib` that refers to it.
- **CUDA Toolkit**: The CUDA Toolkit supplements the CUDA Driver with compilers and additional libraries and header files that are installed into /Developer/NVIDIA/CUDA-10.0 by default. Symlinks are created in /usr/local/cuda/ pointing to their respective files in /Developer/NVIDIA/CUDA-10.0/. Previous installations of the toolkit will be moved to /Developer/NVIDIA/CUDA-#.# to better support side-by-side installations.
- **CUDA Samples (read-only)**: A read-only copy of the CUDA Samples is installed in /Developer/NVIDIA/CUDA-10.0/samples. Previous installations of the samples will be moved to /Developer/NVIDIA/CUDA-#.#/samples to better support side-by-side installations.

A command-line interface is also available:

- **--accept-eula**: Signals that the user accepts the terms and conditions of the CUDA-10.0 EULA.
- **--silent**: No user-input will be required during the installation. Requires **--accept-eula** to be used.
- **--no-window**: No windows will be created during the installation. Useful for installing in environments without a display, such as via ssh. Implies **--silent**. Requires **--accept-eula** to be used.
- **--install-package=<package>**: Specifies a package to install. Can be used multiple times. Options are "cuda-toolkit", "cuda-samples", and "cuda-driver".
- **--log-file=<path>**: Specify a file to log the installation to. Default is /var/log/cuda_installer.log.

Set up the required environment variables:

```bash
export PATH=/Developer/NVIDIA/CUDA-10.0/bin${PATH:+:${PATH}}
export DYLD_LIBRARY_PATH=/Developer/NVIDIA/CUDA-10.0/lib\
                         ${DYLD_LIBRARY_PATH:+:${DYLD_LIBRARY_PATH}}
```

In order to modify, compile, and run the samples, the samples must also be installed with write permissions. A convenience installation script is provided: cuda-install-samples-10.0.sh. This script is installed with the cuda-samples-10-0 package.

To install Nsight Eclipse plugins, an installation script is provided:

```bash
/Developer/NVIDIA/CUDA-10.0/bin/nsight_ee_plugins_manage.sh install <eclipse-dir>
```

Refer to [Nsight Eclipse Plugins Installation Guide](http://docs.nvidia.com/cuda/nsightee-plugins-install-guide/index.html) for more details.

Note: 

To run CUDA applications in console mode on MacBook Pro with both an integrated GPU and a discrete GPU, use the following settings before dropping to console mode:

1. Uncheck **System Preferences** > **Energy Saver** > **Automatic Graphic Switch**
2. Drag the Computer sleep bar to Never in **System Preferences** > **Energy Saver**

#### 0.3.3 Debian/Ubuntu/Linux

##### 0.3.3.1 C/C++ Environment

In order to do so, enable *main repository* in Software & Updates.

Then run these commands in a terminal:

```bash
sudo apt-get update
sudo apt-get install build-essential
```

This will install the following packages:

- [dpkg-dev](https://packages.ubuntu.com/trusty/dpkg-dev) (>= 1.13.5): Debian package development tools

- [g++](https://packages.ubuntu.com/trusty/g++) (>= 4:4.4.3): GNU C++ compiler

- [gcc](https://packages.ubuntu.com/trusty/gcc) (>= 4:4.4.3): GNU C compiler

- [libc6-dev](https://packages.ubuntu.com/trusty/libc6-dev): Embedded GNU C Library: Development Libraries and Header Files

  or [libc-dev](https://packages.ubuntu.com/trusty/libc-dev): virtual package provided by [libc6-dev](https://packages.ubuntu.com/trusty/libc6-dev)

- [make](https://packages.ubuntu.com/trusty/make): An utility for Directing compilation.

##### 0.3.3.2 Java

The default Java version in Ubuntu 18.04 is OpenJDK 10. Once next LTS version OpenJDK 11 is released, it will become the default Java version in Ubuntu 18.04.

Follow the steps below to install Java OpenJDK on an Ubuntu machine:

1. First, update the `apt` package index with:

   ```bash
   sudo apt update
   ```

2. Once the package index is updated install the default Java OpenJDK package with:

   ```bash
   sudo apt install default-jdk
   ```

3. Verify the installation, by running the following command which will print the Java version:

   ```bash
   java -version
   ```

   Then you may see something as:

   ```bash
   openjdk version "10.0.1" 2018-04-17
   OpenJDK Runtime Environment (build 10.0.1+10-Ubuntu-3ubuntu1)
   OpenJDK 64-Bit Server VM (build 10.0.1+10-Ubuntu-3ubuntu1, mixed mode)
   ```

##### 0.3.3.3 Python 3

The newer system starting from 14.04+ should ship with Python 3. If you are on old system or trying to update the newer version, please perform the following lines of commands:

```bash
sudo apt-get update
sudo apt-get upgrade
sudo apt-get dist-upgrade
sudo apt-get install python-dev python-setuptools python-pip python-smbus
```

After all, you may update the `pip`package manager to the latest nightly edition by running:

```bash
python3 -m pip install --user --upgrade pip
```

##### 0.3.3.4 NOAA’s Weather and Climate Toolkit

You may find the latest edition via [NOAA website](<https://www.ncdc.noaa.gov/wct/>). Also, please make sure ==Java== is properly installed. You may find more information about it via its [requirements page](<https://www.ncdc.noaa.gov/wct/requirements.php>).

##### 0.3.3.5 CUDA ==Optional==

1. [Download CUDA](https://developer.nvidia.com/cuda-downloads): I used the 16.04 version and "runfile (local)". That is 1.1 GB.

2. Check the md5 sum:

   ```bash
   md5sum cuda_7.5.18_linux.run
   ```

    Only continue if it is correct.

3. Remove any other installation 

   ```bash
   sudo apt-get purge nvidia-cuda*
   ```

   - if you want to install the drivers too, then

   ```bash
   sudo apt-get purge nvidia-*
   ```

   1. If you want to install the display drivers(*), logout from your GUI. Go to a terminal session (ctrl+alt+F2)

   2. Stop lightdm: `sudo service lightdm stop`

   3. Create a file at `/etc/modprobe.d/blacklist-nouveau.conf` with the following contents: `blacklist nouveau options nouveau modeset=0`

   4. Then do: 

      ```bash
      sudo update-initramfs -u
      ```

      

4. ```bash
   sudo sh cuda_7.5.18_linux.run --override
   ```

   Make sure that you say`y`for the symbolic link.

   Then, start `lightdm` again: 

   ```bash
   sudo service lightdm start
   ```

   

5. Follow the command-line prompts

See also: [NVIDIA CUDA with Ubuntu 16.04 beta on a laptop (if you just cannot wait)](https://www.pugetsystems.com/labs/hpc/NVIDIA-CUDA-with-Ubuntu-16-04-beta-on-a-laptop-if-you-just-cannot-wait-775/)

**Notes**: Yes, there is the possibility to install it via `apt-get install cuda`. I strongly suggest not to use it, as it changes the paths and makes the installation of other tools more difficult.

You might also be interested in [How can I install CuDNN on Ubuntu 16.04?](https://askubuntu.com/q/767269/10425).

==Don't install the display drivers with this script. They are old. Download the latest ones from [Here](<http://www.nvidia.com/Download/index.aspx>).==

Also, make sure to verify CUDA installation.

The following command shows the current CUDA version (last line):

```
$ nvcc --version
nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2016 NVIDIA Corporation
Built on Sun_Sep__4_22:14:01_CDT_2016
Cuda compilation tools, release 8.0, V8.0.44
```

The following command shows your driver version and how much GPU memory you have:

```
$ nvidia-smi
Fri Jan 20 12:19:04 2017       
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 367.57                 Driver Version: 367.57                    |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|===============================+======================+======================|
|   0  GeForce 940MX       Off  | 0000:02:00.0     Off |                  N/A |
| N/A   75C    P0    N/A /  N/A |   1981MiB /  2002MiB |     98%      Default |
+-------------------------------+----------------------+----------------------+

+-----------------------------------------------------------------------------+
| Processes:                                                       GPU Memory |
|  GPU       PID  Type  Process name                               Usage      |
|=============================================================================|
|    0      1156    G   /usr/lib/xorg/Xorg                             246MiB |
|    0      3198    G   ...m,SecurityWarningIconUpdate<SecurityWarni   222MiB |
|    0      6645    C   python                                        1510MiB |
+-----------------------------------------------------------------------------+
```

See also: [Verify CuDNN installation](https://stackoverflow.com/a/36978616/562769)

==Help! The new driver does not work!==

Don't panic. Even if you can't see anything on your computer, the following steps should get you back to the state before:

1. Press shift while startup
2. Go into a root shell
3. Make it writable by `mount -o remount,rw /` (`-` is `?` and `/` is `-` in the american layout)
4. `sh cuda_7.5.18_linux.run --uninstall`
5. `sudo apt-get install nvidia-361 nvidia-common nvidia-prime nvidia-settings`



## 1. Obtain the Toolkits

There are 3 ways to obtain the toolkits.

### 1.1 Direct Download

Fire up a browser, and visit this [awesome page](<https://github.com/nocdoggo/Lake-snow-Effect-Cloud-Identifier>) and find the `Clone or download` icon on the right top of the page.

[![GitHub Clone or Download button](https://www.stevejgordon.co.uk/wp-content/uploads/2018/01/CloneOrDownloadGitHub.png)](https://www.stevejgordon.co.uk/forking-cloning-github/switchtomainrepo)

Then, click on `Download ZIP` to obtain all the files in the repo.

By doing so, you will download everything having been comitted to the repo, including all the testing data and RAW samples. Be prepared since right now, the repo is ==over 2 GB==. Post download process, you may upzip the folder with your favorite utility tool.

### 1.2 GitHub SVN

Please visit [GitHub Desktop Tool page](<https://desktop.github.com/>) to obtain the SVN tool. Then, go back to the this [awesome page](<https://github.com/nocdoggo/Lake-snow-Effect-Cloud-Identifier>) and find the the `Clone or download` icon on the right top of the page.

As shown in the previous image, just click on `Open in Desktop`, you will be able to prompt to make a clone version of the toolkits.

### 1.3 Release Edition

This will happen in the near future.

- Be sure you are in the **Code** view; if not, select the right side `<>` code icon
- Identify the [releases](https://github.com/gnu-mcu-eclipse/qemu/releases) link in the upper line: ![Code releases link](https://gnu-mcu-eclipse.github.io/assets/images/2015/github-qemu-code-tab-releases.png)
- Click the releases link; this will show the Releases view, with the **Latest release** at the top of the page: ![The Latest release view. ](https://gnu-mcu-eclipse.github.io/assets/images/2015/github-qemu-code-tab-latest-release.png)

## 2. Operate the Toolkits

### 2.0 MATLAB Tools

If you are on the elder edition, identify the `run.m` file under the archive. Then, simply click on it to trigger the MATLAB GUI. If you would like to run via command line, please run as:

```bash
matlab -nojvm -nodisplay -nosplash
```

Then, navigate to the archive to run `run.m`.

### 2.1 Python Tools

First, please make sure to have the dependency libraries properly installed. You should not worry about much. Simply run in the terminal as:

```bash
python3 -m pip install -U -r requirements.txt
```

This would simply download all the required libraries from the official sources, compile them, and install to your local machine.

Then, depending on if you would like the GUI or non-GUI edition depending on your work environment, simply execute the `run_GUI.py` or `run.py`. 



## 3. Misc

Should you have any questions, please let us know!