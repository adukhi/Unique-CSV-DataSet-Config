# Unique CSV Data Set Config
## Introduction
*Unique CSV DataSet Config for Jmeter
*This plugin is an extension of JMeter’s CSV Data Set Config component.

## Key Features
1. Ability to provide CSV data only to specified Thread Groups
	* When running tests with multiple Thread Groups, you can configure this plugin to ensure that CSV data is supplied only to certain Thread Groups<br>This allows you to use separate CSV data files for each Thread Group as needed
	
2. Ability to specify the number of data records each Thread can use (unique data allocation)
	* You can predefine the number of data records that each Thread will use, and the plugin assigns unique data to each Thread with no duplication<br>For example, if you have 10 Threads and 100 CSV records, the plugin can distribute 10 unique records to each Thread<br>With this plugin, you can more precisely control data distribution and manage data usage for each Thread in your JMeter tests

## Issues and Solutions of CSV Data Set Config  
1. The CSV Data is consumed by a Thread Group that does not utilize the CSV Data.  
	* CSV Data Set Config  
       . Thread Group B does not use USERID, but it consumes CSV Data, resulting in Thread Group C receiving 3 instead of 2.  
       . Although 100 records of CSV Data were prepared, Thread Group B consumes them, leading to a shortage of CSV Data.  
![](sample/CSVDataSet_NeedToExclusiveAllocation.jpg)
