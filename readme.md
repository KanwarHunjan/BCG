# BCG Case Study
This project uses PySpark to process and analyze large-scale data and is designed to run in a local environment. The primary goal is to load, transform, and analyze data using Spark's distributed computing capabilities while working with configuration settings from a `config.json` file

## Analytics
Application should perform below analysis and store the results for each analysis.
1.	Analytics 1: Find the number of crashes (accidents) in which number of males killed are greater than 2?
2.	Analysis 2: How many two wheelers are booked for crashes? 
3.	Analysis 3: Determine the Top 5 Vehicle Makes of the cars present in the crashes in which driver died and Airbags did not deploy.
4.	Analysis 4: Determine number of Vehicles with driver having valid licences involved in hit and run? 
5.	Analysis 5: Which state has highest number of accidents in which females are not involved? 
6.	Analysis 6: Which are the Top 3rd to 5th VEH_MAKE_IDs that contribute to a largest number of injuries including death
7.	Analysis 7: For all the body styles involved in crashes, mention the top ethnic user group of each unique body style  
8.	Analysis 8: Among the crashed cars, what are the Top 5 Zip Codes with highest number crashes with alcohols as the contributing factor to a crash (Use Driver Zip Code)
9.	Analysis 9: Count of Distinct Crash IDs where No Damaged Property was observed and Damage Level (VEH_DMAG_SCL~) is above 4 and car avails Insurance
10.	Analysis 10: Determine the Top 5 Vehicle Makes where drivers are charged with speeding related offences, has licensed Drivers, used top 10 used vehicle colours and has car licensed with the Top 25 states with highest number of offences (to be deduced from the data)

## Expected Output
1.	Develop an application which is modular & follows software engineering best practices (e.g. Classes, docstrings, functions, config driven, command line executable through spark-submit)
2.	Code should be properly organized in folders as a project
3.	Input data sources and output should be config driven
4.	Code should be strictly developed using Data Frame APIs (Do not use Spark SQL)
5.	Share the entire project as zip or link to project in GitHub repo

Note: All the outputs are stored in the `output` folder within each individual analytics folder

## Features
- Load and parse configurations from a `config.json` file for dynamic processing
- Utilized PySpark to handle large datasets in a distributed manner
- Data transformation capabilities using using Data Frame APIs
- Flexible log path management to track the application's behavior

### Consideration
The following module was created and tested on macos

## Prerequisites
Before running this PySpark project on macOS, ensure the following prerequisites are met:

1. Install Java  
- PySpark requires Java to be installed on your machine.  
- Download the latest version of the Java Development Kit (JDK) from [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html) or install it using Homebrew:  
    ```
    brew install openjdk
    ```
- Set the `JAVA_HOME` environment variable in your shell configuration file (e.g., `.bash_profile`, `.zshrc`):  
    ```
    echo 'export JAVA_HOME=$(/usr/libexec/java_home)' >> ~/.zshrc
    echo 'export PATH=$JAVA_HOME/bin:$PATH' >> ~/.zshrc
    source ~/.zshrc
    ```

2. Install Python  
- Install Python 3.8 or above.  
- Use the default Python package on macOS or install it via [Homebrew](https://brew.sh):  
    ```
    brew install python
    ```

3. Install Apache Spark  
- Download Apache Spark from the official [Apache Spark website](https://spark.apache.org/downloads.html) or use Homebrew:  
    ```
    brew install apache-spark
    ```
- Set the `SPARK_HOME` and update your `PATH`:  
    ```
    echo 'export SPARK_HOME=/usr/local/opt/apache-spark' >> ~/.zshrc
    echo 'export PATH=$SPARK_HOME/bin:$PATH' >> ~/.zshrc
    source ~/.zshrc
    ```

4. Install Hadoop (Optional for File System Support)
- Hadoop is required for HDFS support. Install it via Homebrew:  
  ```bash
  brew install hadoop
  ```

5. Install Required Python Libraries
- Install the necessary Python libraries using `pip`:  
    ```
    pip install pyspark
    ```

6. Verify the Setup 
- Verify Java installation:  
    ```
    java -version
    ```  
- Verify Spark installation:  
    ```
    spark-shell
    ```  
- Verify PySpark:  
    ```
    pyspark
    ```

## Installing
Clone the Github Repo with the URL
```
git clone https://github.com/KanwarHunjan/BCG.git
```

If you are downloading the repository, follow these steps to set it up:
1. Extract the contents of the downloaded ZIP file.  
2. Rename the extracted folder to `BCG` if it has a different name.  
3. Navigate to the `data` folder and extract the `data.zip` file. Ensure all input files are placed directly inside the `BCG/data` folder.  
4. Review the `config.json` file to understand the input and output folder paths. The code is configuration-driven and will automatically use the paths specified in the `config.json` file.

## Steps:
1. Go to the Project Directory: `cd bcg`
2. Spark Submit
   ```
   spark-submit main.py
   ```
Note: Extract all the input csv files from the ZIP file.

## Structure
```
BCG
├─ src
│  ├─ core
│  │  ├─ __init__.py
│  │  └─ car_crash_analysis.py
│  ├─ helpers
│  │  ├─ __init__.py
│  │  └─ utils.py
├─ logs
│  └─ (log folders)
├─ output
│  ├─ analysis_1
│  ├─ analysis_2
│  ├─ analysis_3
│  ├─ analysis_4
│  ├─ analysis_5
│  ├─ analysis_6
│  ├─ analysis_7
│  ├─ analysis_8
│  ├─ analysis_9
│  └─ analysis_10
├─ resources
│  ├─ BCG_Case_Study_CarCrash_Updated_Questions.docx
│  └─ Data Dictionary.xlsx
├─ data
│  └─ data.zip  
├─ config.json
└─ readme.md
```
