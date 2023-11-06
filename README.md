# Introduction
The objective of this project is to create a solution to record and utilize demographic information for a parish.
# Requirements
## Primary Factors
The main requirements that will shape the requirements are:
### Security
+ Due to sensitive nature of data collected, no unauthorized user should have access to this data to either read or write to it
### Safety
+ Data should be safe from destruction either mailiciously or accidentally
+ No modification should be allowed to the data, except via authenticated and authorized users making or reviewing it
### Ease of Access
+ Multiple users to enter data into a common data store
+ Should reduce the friction of gather parish information by allowing people to directly submit their details electronically (with appropriate review)
+ Should leverage the centralized datastore to allow for identifying relationships between data
### Ease of Operation
+ There is no dedicated tech team to support this software, so any operational processess should be automated
+ Steps to perform disaster recovery should be minimal and well documented
## Detailed Requirements
1. Access Control
    1. Any changes to main data store should be via authenticated and authorized users
    1. Mechanism to grant and revoke access to users
1. Backup - Regular Backup of all entered data (periodic or based on data entry)
1. Primary Demographics data (Registration Data)
    1. Migration of existing data from Excel
    1. Optional - Automated entry of existing filled paper forms
    1. Data Entry Form for new entries
        1. Suitable validation of data entered
             + Format: Email, Date format, Telephone numbers, Post Code
             + Relational:
                 + No contact details (phone/email) for under 18s (or under 16s?)
                 + Check against existing emails
                 + (Optional) Address validity
        1. (Optional) Match to existing data against demographics but also Sacrements
1. Sacrements
    1. Data Entry - See specific sacrements for the fields required
    1. Data Linkage - Based on sacrement, combine with general demographic data
    1. Optional - Generate Certificates - Not yet sure if this is feasible 
    1. Sacrements - Baptism
        1. Data Entry Fields:
            + TODO - Capture from paper form 
    1. Sacrements - First Holy Communion
        1. Data Entry Fields:
            + TODO - Capture from paper form
    1. Sacrements - Confirmation
        1. Data Entry Fields:
            + TODO - Capture from paper form
    1. Sacrements - Marriage
        1. Data Entry Fields:
            + TODO - Capture from paper form
    1. Deaths
        1. Data Entry Fields:
            + TODO - Capture from paper form
1. Public Registration Form
    1. Public users can register via a form on the main website
    1. But data should go to a "proposed" list to be reviewed
# Proposed Solution Architecture
    This section is still work in progress
## Technologies
### Service
+ Language: Java - Java 17
+ Build Tool: Maven? (Perhaps Gradle??)
+ Framework: Spring Boot / Spring Data / ???
### Front End
+ Language: Javascript / Html / CSS
+ Build Tool: NPM
+ Framework: React / Redux / Bootstrap
## Platforms
+ Source Control: Git Hub
+ Deployment: GitHub Deployments
+ Domain: demographics.parishdomain.org.uk
+ Hosting: Google Cloud Platform - https://cloud.google.com/
  + Compute: Google App Engine - Standard Java Environment - https://cloud.google.com/appengine/docs/standard/java-gen2/runtime
  + Datastore: Undecided - Firestore vs BigQuery 
    + Firestore: https://cloud.google.com/firestore/pricing
      + 1GB Storage
      + Mongo DB like access patterns
    + BigQuery: https://cloud.google.com/bigquery/pricing
      + 10GB Storage
  + Backup Store: Email + Cloud Storage
  + OCR for existing pre-fill forms
# Application Design Details
    This section has still not started
# Operational Details
    This section has still not started
