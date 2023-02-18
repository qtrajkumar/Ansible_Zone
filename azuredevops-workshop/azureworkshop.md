```yaml
---
pool:
  name: Azure Pipelines
  vmImage: ubuntu-18.04

trigger:
  - master

steps:
  - task: Maven@3
    inputs:
      mavenPomFile: 'pom.xml'
      goals: 'package'
      publishJUnitResults: true
      testResultsFiles: '**/surefire-reports/TEST-*.xml'
      jdkVersionOptions: '1.8'
```


```yaml
---
pool:
  name: Azure Pipelines
  vmImage: ubuntu-22.04

trigger:
  - main

steps:
  - task: Maven@3
    inputs:
      mavenPomFile: 'pom.xml'
      goals: 'package'
      publishJUnitResults: true
      testResultsFiles: '**/surefire-reports/TEST-*.xml'
      jdkVersionOptions: '1.17'
```


* If you observe the above two cases
* Azure Devops allows us to reuse using templates

Azure Pipeline Templates
----------------------------

* [refer here](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/templates?view=azure-devops) for the official docs
* We have created our first reusable template in templates folder
* Now lets create a reusable steps 






