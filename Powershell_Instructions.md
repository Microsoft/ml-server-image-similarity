---
layout: default
title: PowerShell Instructions
---


## PowerShell Instructions
---------------------------

<div class="row">
    <div class="col-md-6">
        <div class="toc">
            <li> <a href="#setup">Setup</a></li>
            <li> <a href="#execute-powershell-script">Execute PowerShell Script</a></li>
            <li> <a href="#score-production-data">Score Production Data</a></li>
            <li> <a href="#review-data">Review Data</a></li>
            <li> <a href="#visualizing-results">Visualizing Results</a> </li>
            <li> <a href="#other-steps">Other Steps</a></li>
        </div>
    </div>
    <div class="col-md-6">
        If you have deployed a VM through the  
        <a href="{{ site.aka_url }}">Azure AI Gallery</a>, all the steps below have already been performed and your database on that machine has all the resulting tables and stored procedures.  You can explore this solution in more detail by examining the folders and running Python or stored procedures to re-create the model, or skip to trying out the model in the included [Jupyter notebook](jupyter.html).
    </div>
</div>

If you are configuring your own server, continue with the steps below to run the PowerShell script.

## Setup 
-----------

First, make sure you have set up your SQL Server by  <a href="SetupSQL.html">following these instructions</a>.  Then proceed with the steps below to run the solution template using the automated PowerShell file. 

## Execute PowerShell Script
----------------------------

Running this PowerShell script will create the data tables and stored procedures for the the operationalization of this solution in R in the `{{ site.db_name }}` database.  It will also execute these procedures to create full database with results of the steps  – dataset creation, modeling, and scoring as described  [here](dba.html).


1. Log onto the machine that contains the SQL Server you wish to use.

2. Download  <a href="https://raw.githubusercontent.com/Microsoft/r-server-campaign-optimization/master/Resources/ActionScripts/SetupVM.ps1" download>SetupVM.ps1</a> to your computer.

1.  Right click on SetupVM.ps1 and select `Run with PowerShell`.

1.  Answer `Y` if asked if it is ok to execute this script.

1. This will make the following modification to your SQL Server:`
    * Creates the SLQRUserGroup for running R and Python code.
    * Reconfigures SQL Server to allow running of external scripts.
    * Installs the latest SQL Server 2017 Cumulative Update if no updates have been installed (this solution requires at least CU1 to run successfully).
    * Clones the solution code and data into the c:\Solutions\{{ site.folder_name }} directory.
    * Installs the image_similarity Python package.
    * Creates the solution database `{{ site.db_name }}` 
    * Enables FILESTREAM at the SQL instance level as described [here](https://docs.microsoft.com/en-us/sql/relational-imagesbases/blob/enable-the-prerequisites-for-filetable).
    * Copies images to the configured filestream directory.
    * Copies the Resnet model needed for this solution into the correct directory.d

    
    
## Review Data
--------------

Once the PowerShell script has completed successfully, log into the SQL Server Management Studio to view all the datasets that have been created in the `{{ site.db_name }}_Py` databases.  
Hit `Refresh` if necessary.
<br/>


[Click here](tables.html) to view the details all tables created in this solution.

## Trying the Model
---------------------

You've now finsihed the process of featurizing images using pre-trained DNN model, preparing the training/testing/evaluation image set, training a multi-class classifier and saving the model into SQL table as [described here](data-scientist.html).

This PowerShell script also created the stored procedures to perform these tasks as well as a procedure that can be used to  return top K similar candidates for new query images. 

You can explore this solution in more detail by examining the folders and running Python or stored procedures to re-create the model, or skip to trying out the model in the included **Test Model.ipynb** [Jupyter notebook](jupyter.html).