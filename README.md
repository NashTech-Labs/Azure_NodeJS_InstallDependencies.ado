# Azure_NodeJS_InstallDependencies.ado
Use this task to install and publish npm packages or to run an npm command. Supports npmjs.com and authenticated registries like Azure Artifacts. This template used for installing the npm dependencies, which install the npm.


## Parameters:

The pipeline requires the following parameters to be defined:

| Name | type | Default | Required/Optional | Comments |
| :-------------: | :-------------: | ------------- | :-------------: | :-------------: |
| filePath | string | $(Build.SourcesDirectory) | Required | define the filepath or working directory for package.json. Youc can also pass arguements  if required |
| npmInstall | String | install  | Optional | another common value used is **ci** |


These parameters provide multiple use case options for the template, enable/disable flags for the utilization of different templates as per the requirements.


## Use Cases

You can directly call a particular template as per the requirement. for example: 

  ```yaml
  # azure-pipeline.yml
  resources:
  repositories:
    - repository: Template
      type: github
      name: your_username/Azure_NodeJS_InstallDependencies.ado
      ref: <respective branch name>
      endpoint: 'githubServiceConnectioNname'

  steps:
  # passing the parameters
  - template: Azure_NodeJS_InstallDependencies.yml
    parameters:
        filePath: ${{ parameters.filePath }}
        npmInstall: ${{ parameters.npmInstall }}
        
Make sure to adjust the repository name, branch name, and parameter values according to your project's requirements.

  ```
