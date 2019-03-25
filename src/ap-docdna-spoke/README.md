# DocDNA Spoke

## Description

A set of Flow Actions to be used in Flow Designer for integration with [Document DNA](https://www.exelatech.com/product/document-dna%C2%AE), a document management solution. The actions make use of a central script include to route SOAP calls.

![DocDNA Spoke Actions](https://raw.githubusercontent.com/platform-experience/api-integration-library/master/src/ap-docdna-spoke/images/ap-docdna-spoke-actions.png)

## Available Actions

* **Query Documents** (by Case Number, Claim Number, Caller ID) returns JSON results & count
* **Get Document** (by Document ID) returns document details JSON, filename, and base64 file
* **Attachment to Record** (select record and include filename & base64) attaches file to record (not directly dependent on DocDNA)

![DocDNA Spoke](https://raw.githubusercontent.com/platform-experience/api-integration-library/master/src/ap-docdna-spoke/images/ap-docdna-spoke.png)

## Installation

Download and install update set **[ap-docdna-spoke.u-update-set.xml](https://github.com/platform-experience/api-integration-library/blob/master/src/ap-docdna-spoke/ap-docdna-spoke.u-update-set.xml)**

* SN Product Documentation - ['Load a customization from a single XML file'](https://docs.servicenow.com/bundle/kingston-application-development/page/build/system-update-sets/task/t_SaveAnUpdateSetAsAnXMLFile.html)

## Configuration

### System Properties

#### Variables for data fields in DocDNA

* **Claim Number**: x_snc_docdna_spoke.docdna.**claim_num_var**
* **Case Number**: x_snc_docdna_spoke.docdna.**case_num_var**
* **Case Date**: x_snc_docdna_spoke.docdna.**case_date_var**
* **ID for Caller**: x_snc_docdna_spoke.docdna.**caller_id_var**
* **ID for Document**: x_snc_docdna_spoke.docdna.**doc_id_var**
* **Content Date**: x_snc_docdna_spoke.docdna.**content_date_var**
* **Folder**: x_snc_docdna_spoke.docdna.**folder_var**

#### Credentials

* x_snc_docdna_spoke.docdna.**endpoint**
* x_snc_docdna_spoke.docdna.**username**
* x_snc_docdna_spoke.docdna.**password**
* x_snc_docdna_spoke.docdna.**production_endpoint**
* x_snc_docdna_spoke.docdna.**production_username**
* x_snc_docdna_spoke.docdna.**production_password**
* x_snc_docdna_spoke.docdna.**production** – Use production credentials?
* x_snc_docdna_spoke.docdna.**rpt_id** – Report ID