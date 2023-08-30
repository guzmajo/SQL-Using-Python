<center>
    <img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/FinalModule_Coursera_V5/images/SN_web_lightmode.png" width="300" alt="cognitiveclass.ai logo">
</center>

<h1 align=center><font size = 5>Assignment: Notebook for Peer Assignment</font></h1>


# Introduction

Using this Python notebook you will:

1.  Understand three Chicago datasets
2.  Load the three datasets into three tables in a SQLIte database
3.  Execute SQL queries to answer assignment questions


## Understand the datasets

To complete the assignment problems in this notebook you will be using three datasets that are available on the city of Chicago's Data Portal:

1.  <a href="https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2021-01-01">Socioeconomic Indicators in Chicago</a>
2.  <a href="https://data.cityofchicago.org/Education/Chicago-Public-Schools-Progress-Report-Cards-2011-/9xs2-f89t?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2021-01-01">Chicago Public Schools</a>
3.  <a href="https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-present/ijzp-q8t2?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2021-01-01">Chicago Crime Data</a>

### 1. Socioeconomic Indicators in Chicago

This dataset contains a selection of six socioeconomic indicators of public health significance and a “hardship index,” for each Chicago community area, for the years 2008 – 2012.

A detailed description of this dataset and the original dataset can be obtained from the Chicago Data Portal at:
[https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2](https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2021-01-01&cm_mmc=Email_Newsletter-_-Developer_Ed%2BTech-_-WW_WW-_-SkillsNetwork-Courses-IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork-20127838&cm_mmca1=000026UJ&cm_mmca2=10006555&cm_mmca3=M12345678&cvosrc=email.Newsletter.M12345678&cvo_campaign=000026UJ)

### 2. Chicago Public Schools

This dataset shows all school level performance data used to create CPS School Report Cards for the 2011-2012 school year. This dataset is provided by the city of Chicago's Data Portal.

A detailed description of this dataset and the original dataset can be obtained from the Chicago Data Portal at:
[https://data.cityofchicago.org/Education/Chicago-Public-Schools-Progress-Report-Cards-2011-/9xs2-f89t](https://data.cityofchicago.org/Education/Chicago-Public-Schools-Progress-Report-Cards-2011-/9xs2-f89t?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2021-01-01&cm_mmc=Email_Newsletter-_-Developer_Ed%2BTech-_-WW_WW-_-SkillsNetwork-Courses-IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork-20127838&cm_mmca1=000026UJ&cm_mmca2=10006555&cm_mmca3=M12345678&cvosrc=email.Newsletter.M12345678&cvo_campaign=000026UJ)

### 3. Chicago Crime Data

This dataset reflects reported incidents of crime (with the exception of murders where data exists for each victim) that occurred in the City of Chicago from 2001 to present, minus the most recent seven days.

A detailed description of this dataset and the original dataset can be obtained from the Chicago Data Portal at:
[https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-present/ijzp-q8t2](https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-present/ijzp-q8t2?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2021-01-01&cm_mmc=Email_Newsletter-_-Developer_Ed%2BTech-_-WW_WW-_-SkillsNetwork-Courses-IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork-20127838&cm_mmca1=000026UJ&cm_mmca2=10006555&cm_mmca3=M12345678&cvosrc=email.Newsletter.M12345678&cvo_campaign=000026UJ)


### Download the datasets

This assignment requires you to have these three tables populated with a subset of the whole datasets.

In many cases the dataset to be analyzed is available as a .CSV (comma separated values) file, perhaps on the internet. Click on the links below to download and save the datasets (.CSV files):

*   <a href="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/FinalModule_Coursera_V5/data/ChicagoCensusData.csv?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2021-01-01" target="_blank">Chicago Census Data</a>

*   <a href="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/FinalModule_Coursera_V5/data/ChicagoPublicSchools.csv?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2021-01-01" target="_blank">Chicago Public Schools</a>

*   <a href="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/FinalModule_Coursera_V5/data/ChicagoCrimeData.csv?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2021-01-01" target="_blank">Chicago Crime Data</a>

**NOTE:** Ensure you have downloaded the datasets using the links above instead of directly from the Chicago Data Portal. The versions linked here are subsets of the original datasets and have some of the column names modified to be more database friendly which will make it easier to complete this assignment.


### Store the datasets in database tables

To analyze the data using SQL, it first needs to be loaded into SQLite DB.
We will create three tables in as under:

1.  **CENSUS_DATA**
2.  **CHICAGO_PUBLIC_SCHOOLS**
3.  **CHICAGO_CRIME_DATA**

Let us now load the ipython-sql  extension and establish a connection with the database

* Here you will be loading the csv files into the pandas Dataframe and then loading the data into the above mentioned sqlite tables.

* Next you will be connecting to the sqlite database  **FinalDB**.

Refer to the previous lab for hints .

<a href ="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/Module%205/DB0201EN-Week3-1-4-Analyzing_SQLite.ipynb">Hands-on Lab: Analyzing a real World Data Set</a>






```python
%load_ext sql
```


```python
import csv, sqlite3

con = sqlite3.connect("chicagodataset.db")
cur = con.cursor()
!pip install -q pandas==1.1.5
```


```python
%sql sqlite:///chicagodataset.db
```


```python
import pandas
df = pandas.read_csv('ChicagoCrimeData.csv')
df.to_sql("ChicagoCrimeData", con, if_exists='replace', index=False,method="multi")
```


```python
import pandas
df = pandas.read_csv('ChicagoCensusData.csv')
df.to_sql("ChicagoCensusData", con, if_exists='replace', index=False,method="multi")
```


```python
import pandas
df = pandas.read_csv('ChicagoPublicSchools.csv')
df.to_sql("ChicagoPublicSchools", con, if_exists='replace', index=False,method="multi")
```

    C:\Users\LENOVO\anaconda3\lib\site-packages\pandas\core\generic.py:2605: UserWarning: The spaces in these column names will not be changed. In pandas versions < 0.14, spaces were converted to underscores.
      sql.to_sql(
    


```python
%sql SELECT * FROM ChicagoCrimeData limit 5;
```

     * sqlite:///chicagodataset.db
    Done.
    




<table>
    <thead>
        <tr>
            <th>ID</th>
            <th>CASE_NUMBER</th>
            <th>DATE</th>
            <th>BLOCK</th>
            <th>IUCR</th>
            <th>PRIMARY_TYPE</th>
            <th>DESCRIPTION</th>
            <th>LOCATION_DESCRIPTION</th>
            <th>ARREST</th>
            <th>DOMESTIC</th>
            <th>BEAT</th>
            <th>DISTRICT</th>
            <th>WARD</th>
            <th>COMMUNITY_AREA_NUMBER</th>
            <th>FBICODE</th>
            <th>X_COORDINATE</th>
            <th>Y_COORDINATE</th>
            <th>YEAR</th>
            <th>LATITUDE</th>
            <th>LONGITUDE</th>
            <th>LOCATION</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>3512276</td>
            <td>HK587712</td>
            <td>2004-08-28</td>
            <td>047XX S KEDZIE AVE</td>
            <td>890</td>
            <td>THEFT</td>
            <td>FROM BUILDING</td>
            <td>SMALL RETAIL STORE</td>
            <td>0</td>
            <td>0</td>
            <td>911</td>
            <td>9</td>
            <td>14.0</td>
            <td>58.0</td>
            <td>6</td>
            <td>1155838.0</td>
            <td>1873050.0</td>
            <td>2004</td>
            <td>41.807440500000006</td>
            <td>-87.70395585</td>
            <td>(41.8074405, -87.703955849)</td>
        </tr>
        <tr>
            <td>3406613</td>
            <td>HK456306</td>
            <td>2004-06-26</td>
            <td>009XX N CENTRAL PARK AVE</td>
            <td>820</td>
            <td>THEFT</td>
            <td>$500 AND UNDER</td>
            <td>OTHER</td>
            <td>0</td>
            <td>0</td>
            <td>1112</td>
            <td>11</td>
            <td>27.0</td>
            <td>23.0</td>
            <td>6</td>
            <td>1152206.0</td>
            <td>1906127.0</td>
            <td>2004</td>
            <td>41.89827996</td>
            <td>-87.71640551</td>
            <td>(41.898279962, -87.716405505)</td>
        </tr>
        <tr>
            <td>8002131</td>
            <td>HT233595</td>
            <td>2011-04-04</td>
            <td>043XX S WABASH AVE</td>
            <td>820</td>
            <td>THEFT</td>
            <td>$500 AND UNDER</td>
            <td>NURSING HOME/RETIREMENT HOME</td>
            <td>0</td>
            <td>0</td>
            <td>221</td>
            <td>2</td>
            <td>3.0</td>
            <td>38.0</td>
            <td>6</td>
            <td>1177436.0</td>
            <td>1876313.0</td>
            <td>2011</td>
            <td>41.81593313</td>
            <td>-87.62464213</td>
            <td>(41.815933131, -87.624642127)</td>
        </tr>
        <tr>
            <td>7903289</td>
            <td>HT133522</td>
            <td>2010-12-30</td>
            <td>083XX S KINGSTON AVE</td>
            <td>840</td>
            <td>THEFT</td>
            <td>FINANCIAL ID THEFT: OVER $300</td>
            <td>RESIDENCE</td>
            <td>0</td>
            <td>0</td>
            <td>423</td>
            <td>4</td>
            <td>7.0</td>
            <td>46.0</td>
            <td>6</td>
            <td>1194622.0</td>
            <td>1850125.0</td>
            <td>2010</td>
            <td>41.74366532</td>
            <td>-87.56246276</td>
            <td>(41.743665322, -87.562462756)</td>
        </tr>
        <tr>
            <td>10402076</td>
            <td>HZ138551</td>
            <td>2016-02-02</td>
            <td>033XX W 66TH ST</td>
            <td>820</td>
            <td>THEFT</td>
            <td>$500 AND UNDER</td>
            <td>ALLEY</td>
            <td>0</td>
            <td>0</td>
            <td>831</td>
            <td>8</td>
            <td>15.0</td>
            <td>66.0</td>
            <td>6</td>
            <td>1155240.0</td>
            <td>1860661.0</td>
            <td>2016</td>
            <td>41.773455299999995</td>
            <td>-87.70648047</td>
            <td>(41.773455295, -87.706480471)</td>
        </tr>
    </tbody>
</table>



## Problems

Now write and execute SQL queries to solve assignment problems

### Problem 1

##### Find the total number of crimes recorded in the CRIME table.



```python
%sql SELECT COUNT (*) FROM ChicagoCrimeData;
```

     * sqlite:///chicagodataset.db
    Done.
    




<table>
    <thead>
        <tr>
            <th>COUNT (*)</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>533</td>
        </tr>
    </tbody>
</table>



### Problem 2

##### List community areas with per capita income less than 11000.



```python
%sql SELECT COMMUNITY_AREA_NAME, PER_CAPITA_INCOME FROM ChicagoCensusData WHERE PER_CAPITA_INCOME < 11000;
```

     * sqlite:///chicagodataset.db
    Done.
    




<table>
    <thead>
        <tr>
            <th>COMMUNITY_AREA_NAME</th>
            <th>PER_CAPITA_INCOME</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>West Garfield Park</td>
            <td>10934</td>
        </tr>
        <tr>
            <td>South Lawndale</td>
            <td>10402</td>
        </tr>
        <tr>
            <td>Fuller Park</td>
            <td>10432</td>
        </tr>
        <tr>
            <td>Riverdale</td>
            <td>8201</td>
        </tr>
    </tbody>
</table>



### Problem 3

##### List all case numbers for crimes  involving minors?(children are not considered minors for the purposes of crime analysis)



```python
%sql SELECT DISTINCT CASE_NUMBER FROM ChicagoCrimeData where DESCRIPTION like '%MINOR%'
```

     * sqlite:///chicagodataset.db
    Done.
    




<table>
    <thead>
        <tr>
            <th>CASE_NUMBER</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>HL266884</td>
        </tr>
        <tr>
            <td>HK238408</td>
        </tr>
    </tbody>
</table>



### Problem 4

##### List all kidnapping crimes involving a child?



```python
%sql SELECT COUNT (*), PRIMARY_TYPE, DESCRIPTION FROM ChicagoCrimeData WHERE PRIMARY_TYPE LIKE 'K%';
```

     * sqlite:///chicagodataset.db
    Done.
    




<table>
    <thead>
        <tr>
            <th>COUNT (*)</th>
            <th>PRIMARY_TYPE</th>
            <th>DESCRIPTION</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>KIDNAPPING</td>
            <td>CHILD ABDUCTION/STRANGER</td>
        </tr>
    </tbody>
</table>



### Problem 5

##### What kinds of crimes were recorded at schools?



```python
%sql SELECT DISTINCT(PRIMARY_TYPE) FROM ChicagoCrimeData WHERE LOCATION_DESCRIPTION LIKE '%SCHOOL%'
```

     * sqlite:///chicagodataset.db
    Done.
    




<table>
    <thead>
        <tr>
            <th>PRIMARY_TYPE</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>BATTERY</td>
        </tr>
        <tr>
            <td>CRIMINAL DAMAGE</td>
        </tr>
        <tr>
            <td>NARCOTICS</td>
        </tr>
        <tr>
            <td>ASSAULT</td>
        </tr>
        <tr>
            <td>CRIMINAL TRESPASS</td>
        </tr>
        <tr>
            <td>PUBLIC PEACE VIOLATION</td>
        </tr>
    </tbody>
</table>



### Problem 6

##### List the average safety all for each type of school.



```sql
%%sql
    
SELECT "Elementary, Middle, or High School",AVG(SAFETY_SCORE) AS AVERAGE_SAFETY_SCORE
FROM ChicagoPublicSchools
GROUP BY "Elementary, Middle, or High School";
```

     * sqlite:///chicagodataset.db
    Done.
    




<table>
    <thead>
        <tr>
            <th>Elementary, Middle, or High School</th>
            <th>AVERAGE_SAFETY_SCORE</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>ES</td>
            <td>49.52038369304557</td>
        </tr>
        <tr>
            <td>HS</td>
            <td>49.62352941176471</td>
        </tr>
        <tr>
            <td>MS</td>
            <td>48.0</td>
        </tr>
    </tbody>
</table>



### Problem 7

##### List 5 community areas with highest % of households below poverty line



```sql
%%sql

SELECT COMMUNITY_AREA_NAME, PERCENT_HOUSEHOLDS_BELOW_POVERTY
FROM ChicagoCensusData
ORDER BY PERCENT_HOUSEHOLDS_BELOW_POVERTY DESC
LIMIT 5 ;
```

     * sqlite:///chicagodataset.db
    Done.
    




<table>
    <thead>
        <tr>
            <th>COMMUNITY_AREA_NAME</th>
            <th>PERCENT_HOUSEHOLDS_BELOW_POVERTY</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Riverdale</td>
            <td>56.5</td>
        </tr>
        <tr>
            <td>Fuller Park</td>
            <td>51.2</td>
        </tr>
        <tr>
            <td>Englewood</td>
            <td>46.6</td>
        </tr>
        <tr>
            <td>North Lawndale</td>
            <td>43.1</td>
        </tr>
        <tr>
            <td>East Garfield Park</td>
            <td>42.4</td>
        </tr>
    </tbody>
</table>



### Problem 8

##### Which community area is most crime prone?



```sql
%%sql

SELECT CCD.COMMUNITY_AREA_NUMBER ,COUNT(CCD.COMMUNITY_AREA_NUMBER) AS FREQUENCY
FROM ChicagoCrimeData AS CCD 
GROUP BY CCD.COMMUNITY_AREA_NUMBER
ORDER BY COUNT(CCD.COMMUNITY_AREA_NUMBER) DESC
LIMIT 1;
```

     * sqlite:///chicagodataset.db
    Done.
    




<table>
    <thead>
        <tr>
            <th>COMMUNITY_AREA_NUMBER</th>
            <th>FREQUENCY</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>25.0</td>
            <td>43</td>
        </tr>
    </tbody>
</table>



Double-click **here** for a hint

<!--
Query for the 'community area number' that is most crime prone.
-->


### Problem 9

##### Use a sub-query to find the name of the community area with highest hardship index



```sql
%%sql

SELECT COMMUNITY_AREA_NAME
FROM  ChicagoCensusData
WHERE HARDSHIP_INDEX = (SELECT MAX(HARDSHIP_INDEX) FROM ChicagoCensusData);
```

     * sqlite:///chicagodataset.db
    Done.
    




<table>
    <thead>
        <tr>
            <th>COMMUNITY_AREA_NAME</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Riverdale</td>
        </tr>
    </tbody>
</table>



### Problem 10

##### Use a sub-query to determine the Community Area Name with most number of crimes?



```sql
%%sql

SELECT community_area_name
FROM ChicagoCensusData 
WHERE COMMUNITY_AREA_NUMBER = (    
    SELECT CCD.COMMUNITY_AREA_NUMBER 
    FROM ChicagoCrimeData AS CCD 
    GROUP BY CCD.COMMUNITY_AREA_NUMBER
    ORDER BY COUNT(CCD.COMMUNITY_AREA_NUMBER) DESC
    LIMIT 1)

LIMIT 1;
```

     * sqlite:///chicagodataset.db
    Done.
    




<table>
    <thead>
        <tr>
            <th>COMMUNITY_AREA_NAME</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Austin</td>
        </tr>
    </tbody>
</table>



Copyright © 2020 This notebook and its source code are released under the terms of the [MIT License](https://bigdatauniversity.com/mit-license?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2021-01-01&cm_mmc=Email_Newsletter-_-Developer_Ed%2BTech-_-WW_WW-_-SkillsNetwork-Courses-IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork-20127838&cm_mmca1=000026UJ&cm_mmca2=10006555&cm_mmca3=M12345678&cvosrc=email.Newsletter.M12345678&cvo_campaign=000026UJ).


## Author(s)

<h4> Hima Vasudevan </h4>
<h4> Rav Ahuja </h4>
<h4> Ramesh Sannreddy </h4>

## Contribtuor(s)

<h4> Malika Singla </h4>

## Change log

| Date       | Version | Changed by        | Change Description                             |
| ---------- | ------- | ----------------- | ---------------------------------------------- |
| 2022-03-04 | 2.5     | Lakshmi Holla     | Changed markdown.                   |
| 2021-05-19 | 2.4     | Lakshmi Holla     | Updated the question                           |
| 2021-04-30 | 2.3     | Malika Singla     | Updated the libraries                          |
| 2021-01-15 | 2.2     | Rav Ahuja         | Removed problem 11 and fixed changelog         |
| 2020-11-25 | 2.1     | Ramesh Sannareddy | Updated the problem statements, and datasets   |
| 2020-09-05 | 2.0     | Malika Singla     | Moved lab to course repo in GitLab             |
| 2018-07-18 | 1.0     | Rav Ahuja         | Several updates including loading instructions |
| 2018-05-04 | 0.1     | Hima Vasudevan    | Created initial version                        |

## <h3 align="center"> © IBM Corporation 2020. All rights reserved. <h3/>



```python
jupyter nbconvert --to markdown DB0201EN-PeerAssign-v5_SQLite.ipynb
```


      Input In [62]
        jupyter nbconvert --to markdown DB0201EN-PeerAssign-v5_SQLite.ipynb
                ^
    SyntaxError: invalid syntax
    

