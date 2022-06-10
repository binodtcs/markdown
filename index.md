# Cypress framework for automation of Web UI testing
Below is the details to use this framework for web UI automation

## Steps to start your own automation using this boilerplate as a template
  1. ### **Creating your own repository**
  
     - Create your own project by clicking at "Use this template" on the top of this page
    
       ![image](docs/Use_template.png)
    
  2. ### **Confirm the new repository details**
  
      - Confirm the organisation, fill your repository name, the description, ensure to permit only internal access and click at "Create repository from template"
    
        ![image1](docs/screenshot_template.png)
    
  3. ### **Check-out the new project**
  
      We are going to show how to checkout your new project. Remember the name you used before to create your project template
      
      ```git clone https://github.com/RoyalAholdDelhaize/your-test-automation-script-name.git```
    
   4. ### **Configuration**
   
      - #### *Add the formatter in the project based on the machine OS. (This is used to run/execute the automation)*
         - Download the latest release of the cucumber-json-formatter based on machine OS
            
            [Release-Cucumber-formatter](https://github.com/cucumber/common/releases)
            
         - Place the downloaded file in the formatter folder & rename the file as *cucumber-json-formatter*  for Mac & Linux, For Windows rename it to *cucumber-json-formatter.exe*
         
            ![image2](docs/formatter_sample.png)
            
         -  Update the file name in the package.json file under **cypress-cucumber-preprocessor** section as shown below. *Windows example:*
         
            ![image3](docs/package_json.png)
            
      - #### *Update the publisher.mjs file to publish the test reports to Zephyr Scale*
         -  *const projectKey = 'XX'* in place of XX provide the projectKey of your project
         -  *const zipFilePath = 'XXXXXXXX'* in place of XXXXXXXX provide the path of the zip reports. For current boiler plate the path is : './reports/testResults.zip'
         -  *const sourceFilePath = 'XXXXXXXX'* in place of XXXXXXXX provide the path of the json reports. For current boiler plate the path is : './reports/cucumber-report.json'
         -  Set or Export the environment variable *ZEPHYR_TOKEN* with the value generated post clicking on Zephyr Scale API Access Tokens in your system
         
             ![image4](docs/zephyr_token.png)
             
             
   5. ### **Execution**
    
      - Install Cypress & its' dependencies as mentioned in package.json file of the boilerplate `npm install`
      
      - To run the all the scenarios & publish the report to Zephyr Scale. Execute the command `npm run test-publish`
      
      - To run the scenarios based on tags. Execute the command `npm run test-tags`
      
      - To publish reports to Zephyr Scale run the command. Execute the command `node publisher.mjs`
      
   6. ### **Report**
    
      A JSON report will be generated after the test execution is completed. This file will be saved in the reports folder under the name *cucumber-report.json*
      
   7. ### **CI/CD**
   
      Github Action workflow is also available in this boilerplate. It can be changed in the *pipeline_test.yml* file.
      
      Currently it is set as run the script manually, but it can be changed to kick off the execution based on a pull request/on check-in.
      
      Please refer the Github Action document for further information.
      
      [Github_Action](https://docs.cypress.io/guides/continuous-integration/github-actions#Caching-Dependencies-and-Build-Artifacts)
