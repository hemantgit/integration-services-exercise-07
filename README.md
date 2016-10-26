# Backbase Training Exercises

## Portal Backend - Module 7: Yet another REST example

This example provides an example of REST call, simulating a datasource for the *accounts widget* of the *retail collection*.

### Installation & Configuration

- Clone this project into the **services** folder of your project

- Include integration-services-exercise-07 module to the build. Open `services/pom.xml` and add **integration-services-exercise-07** in the `<modules>` section:
	```xml
	    <modules>
	        ...	    
	        <module>integration-services-exercise-07</module>
	        ...
	    </modules>
	```	
	Re-compile **services** by executing `mvn clean install` in the **services** folder.

- Add the newly created module in the Portal application. In the `<dependencies>` section of `webapps/portalserver/pom.xml`, add the following dependency:

	```xml
	    <dependency>
	        <groupId>com.backbase.training</groupId>
	        <artifactId>integration-services-exercise-07</artifactId>
	        <version>1.0-SNAPSHOT</version>
	    </dependency>
	```

If you are already running portal server, stop your jetty server. Otherwise, just proceed with the next step.     

### Run & Test

- If Portal Server is already running, stop it by pressing *Ctrl+C*. Start Portal Server application by executing `mvn jetty:run` command from the **webapps/portalserver** directory.
- Call the REST service.
	
```javascript
GET localhost:7777/portalserver/services/rest/v2/customer-assets
```	

It will return a list of accounts.

You can also drag and drop the *accounts* widget into a portal page. You should change the *accounts data source* property to *$(servicesPath)/services/rest/v2/customer-assets*




	
	
	
