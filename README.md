# Statistics-Report-Analysis
GoldenGate Report File Analysis Utility with Automatic XLS File Generation


Prerequisites:

    JDK 1.8 minimum
	
Launching the utility: 

	java -cp ooxml-schemas-1.4.jar -jar reportAnalysis.jar report_file_directory frequency
	
The frequency allows transactions to be summed per minute.
Example: with 60 we sum the insert/update/delete passed in 1 hour
	
Sample :

	java -cp ooxml-schemas-1.4.jar -jar reportAnalysis.jar /app/goldengate/deploy/var/lib/report 60
	
The result files are generated in the same directory as that which contains the report files.
In the Excel sheet, we have 3 sheets :

	- The summary of insert, update and delete since the start of the process and the deltas according to the frequency parameters
	- Trail switch periods
	- Details by table and by transaction, cumulatively and in delta. To have this detail it is necessary to put in the extract and replicat report at xx:yy parameter files. To have the detail by hour for example set :

report at 00:00
report at 01:00
report at 02:00
....
report at 21:00
report at 22:00
report at 23:00

Summary : 
![image](https://github.com/StephaneBraun/Statistics-Report-Analysis/assets/119328984/eed02e12-b0aa-45fd-9859-ed31460710d5)

Trails : 

![image](https://github.com/StephaneBraun/Statistics-Report-Analysis/assets/119328984/b486b292-9098-4af0-a1b6-e906c7601477)

Tables detail : 

![image](https://github.com/StephaneBraun/Statistics-Report-Analysis/assets/119328984/1f05917b-a5e5-44f2-a310-40493e742eb6)


