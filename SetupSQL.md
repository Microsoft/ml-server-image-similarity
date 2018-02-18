---
layout: default
title: "On-Prem: Setup SQL Server 2017"
---

## On-Prem: Setup SQL Server
--------------------------

<div class="row">
    <div class="col-md-6">
        <div class="toc">
            <li><a href="#prepare-your-sql-server-installation">Prepare your SQL Server  Installation</a></li>
            <li><a href="#ready-to-run-code">Ready to Run Code</a></li>
        </div>
    </div>
    <div class="col-md-6">
        The instructions on this page will help you to add this solution to your on premises SQL Server 2016 or higher.  
        <p>
        If you instead would like to try this solution out on a virtual machine, visit the <a href="{{ site.aka_url }}">Azure AI Gallery</a> and use the Deploy button.  All the configuration described below will be done for you, as well as the initial deployment of the solution. </p>
    </div>
</div>

## Prepare your SQL Server Installation
-------------------------------------------

The rest of this page assumes you are configuring your on premises SQL Server 2016 or 2017 for this solution.

If you need a trial version of SQL Server see [What's New in SQL Server 2016](https://msdn.microsoft.com/en-us/library/bb500435.aspx) or [What's New in SQL Server 2017](https://docs.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-2017)for download or VM options. 

Complete the steps in the Set up Microsoft Machine Learning Services (In-Database) Instructions. The set up instructions file can found at  <a href="https://msdn.microsoft.com/en-us/library/mt696069.aspx" target="_blank"> https://msdn.microsoft.com/en-us/library/mt696069.aspx</a>


### Ready to Run Code 
---------------------

You are now ready to run the code for this solution.  

* Install the solution by following these <a href="Powershell_Instructions.html">PowerShell Instructions</a> for deployment.

* Typically a data scientist will create and test a predictive model from their favorite R IDE, at which point the models will be stored in SQL Server and then scored in production using Transact-SQL (T-SQL) stored procedures. 
You can follow along with this by following the steps in [For the Data Scientist](data-scientist.html) or [For the Database Analyst](dba.html).


	