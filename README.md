# PPODtottl

This is code to convert Patrick Huber's highly interlinked Google Sheets document
containing PPOD information (Persons, Project, Organizations, and Datasets) 
into an RDF turtle file.

Files in this repository:

* README.md - this README file
* PPODtottl.py - main Python script for conversion of Google Sheets document to RDF file
* PPODtottl.ipynb - Jupyter notebook for data conversion, now deprecated
* PPOD0.ttl - output RDF file (Turtle format)
* CACounties_WD.csv - lookup table giving URIs for the counties
* CWHR_Habitat_Lookup_Table.csv - lookup table matching habitat codes to full names

A template for the Google Sheets spreadsheet is available at https://docs.google.com/spreadsheets/d/1B4DVedZarxwY4t1at6PfbNrMBzmohz6pn1Se_zPFQwo/edit?usp=sharing. This template has had the data records deleted.

The Python script PPODtottl.py requires the following libraries: gspread, pandas, binascii, rdflib, pprint, and oauth2client.service_account. 

The script has been tested under Python 3.6.9 and is run with the command `python ./PPODtottl.py`. The script produces output in the file `PPOD0.ttl`. This filename can be changed by editing the `writegraph` function in the script.

By necessity, the script connects to Google Sheets and requires authorization to retrieve data from the spreadsheet. This is handled by the functions `oauth2client.service_account.ServiceAccountCredentials` and `gspread`. The user of the script needs to create a Google Service Account for this task; tutorials on making this connection are available at https://blog.coupler.io/python-to-google-sheets/ and https://developers.google.com/sheets/api/guides/authorizing.


