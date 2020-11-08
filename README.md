The priate Jack Sparrow wants to know what Ad campaign got him most customers [almost all startups face this problem].
<br  /> 
<br  /> 
#Following is the Ad analytics capturing infrastructure of Jack Sparrow's Startup
<br>
<img src="https://github.com/cdevairakkam7/data_engineering/blob/main/Ads%20Infrastructure.png" width="350" height="300" />
<br  /> 
<br  /> 
#Signup / Conversion data of Jack Sparrow has the following data flow
<br>
<img src="https://github.com/cdevairakkam7/data_engineering/blob/main/Signup%20:%20Conversion%20data.png" width="350" height="400" />
<br  /> 
<br  />
Now the data warehouse has ads data and sign up data under one roof.
<br>
Next step is to connect a BI tool like Mode Analytics, Chartio or looker and query the data using SQL.
<br> 
#Although this method works and gets us desired results this has a lot of issues.

* Data in our data warehouse is not validated against
  * Null Check 
  * Foreign key primary key relationship 
  * Uniqueness
  * dateformat check 
* The entire schema and all columns have to be exposed to the BI tool and to the end user to successfully build dashboards
* No failure logging capability around data migration from 3rd party, production DB to data warehouse
<br  /> 
<br  />
In order to circumvent these issues we bring data build tool into play.
<br>
#Using DBT we can perform 
<br/>
* Null Check
* Foreign key primary key relationship
* Uniqueness
* dateformat check
* Use Jinja to slice and dice data
* Use snapshot to go back in time
<br  /> 
<br  />
Plugging DBT into our data warehouse looks like the following 
<img src="https://github.com/cdevairakkam7/data_engineering/blob/main/DBT%20Infrastructure.png"width="600" height="500" />
<br  /> 
<br  />
Now we just have to connect the Analytics schema to the BI tool and our end users need to query consolidated tables to build dashboards
