# Demo Notes

Notes, tips, and hints for using the various Veracode scan types with this application.

Also see the `docs/flaws` folder for in-depth explanations of the various exploits exposed in this application.

## Static scanning

Build the app:

	zip -r verademo-python.zip app verademo-python *.py requirements.txt -x "*__pycache__*" 

The verademo-python.zip file is the file to upload for scanning. Either upload this file to the Veracode platform for a Policy/Sandbox scan, or use it with the Veracode Pipeline scan.

## SCA scanning

### Upload/Scan

This will just happen as part of the Policy or Sandbox scan.

### Agent-based scan

Use either the command-line version of the SCA agent (follow the install and config instructions in the Veracode [docs center](https://docs.veracode.com/r/c_sc_what_is) ) or the IDE plugin to initiate an SCA scan.

### Vulnerable Methods

The Veracode agent-based SCA scan can also find [vulnerable methods](https://docs.veracode.com/r/Finding_and_Fixing_Vulnerabilities#fixing-vulnerable-methods).  In this app, there is a vulnerable version of the md5hash library called from both the `User` and `UserController` classes.

### SBOM generation

SBOM generation for the application is supported after an SCA scan ([link](https://docs.veracode.com/r/Generating_a_Software_Bill_of_Materials_SBOM_for_Upload_Scans)) 

SBOM generation for the Docker container is supported by the Container/CLI scanner ([link](https://docs.veracode.com/r/veracode_sbom)).

## Veracode Fix

This application has flaws that can be fixed with [Veracode Fix](https://docs.veracode.com/r/veracode_fix).  For an example of one:

