SetNetLoc
=========

Purpose
--------------
Programmatically update MyNetwork and Location definition of FA. 
 
General
--------------
- It can run on Windows and Linux OS;
- The client API must run at JDK/JRE 1.5 or above;
- It is a standalone command-line client application, independence of FA GUI (jars);
- It simulates FA GUI to send the MyNetwork and Location setting requests to FA server. So it can run remotely, not limited on the target FA host;
- No need restart FA server after run it;
- You even do not need restart FA GUI even if one GUI session is available, by design the change can be reflected automatically on FA GUI;
 
Release notes
--------------
- 1.0	Initial version
- 1.1	Support HTTP POST
- 1.2	Support IP as FA address
- 1.3	Support big Location file
 
Input
--------------
- FA_USER_NAME: FA User name
- FA_PASSWORD: FA Password
- FA_DOMAIN_NAME: FA Host IP or Domain name
- LOC_CSV_FILE: the location csv file 
- MyNetwork_CSV_FILE: the network csv file

Notes on the input CSV files:
 - Follow the format what FA bulk export generates and which can used to import into FA. 
 - It is a full definition;
 - No validation;
 
Usage
--------------
The running script:
- SetNetAndLoc_run.sh  (Unix/Linux)
- SetNetAndLoc_run.bat  (Windows)

* Command Line (Recommended), taking Windows for example:

./SetNetAndLoc_run.sh --context_param FA_USER_NAME=FA_admin --context_param FA_PASSWORD=admin1234 --context_param FA_DOMAIN_NAME=fa.calix.com --context_param LOC_CSV_FILE=/root/csv/Location.csv --context_param MyNetwork_CSV_FILE=/root/csv/Network.csv

Note that every parameter in command line requires the token --context_param.

* Configuration file

All of configurations can be pre-set in the property file - Default.properties: SetNetAndLoc_<Version>/SetNetAndLoc/test/setnetandloc_<Version>/contexts/Default.properties, then just concisely run the script without any parameter