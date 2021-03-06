# Web Forms for Marketers module for Sitecore XDB Environment

<a href="http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FSitecore%2Fsitecore-azure-quickstart-templates%2Fmaster%2FWFFM%208.2.3%2Fxdb%2Fazuredeploy.json" target="_blank">
    <img src="http://armviz.io/visualizebutton.png"/>
</a>

This template deploys Web Forms for Marketers module into a Sitecore XDB Environment (Processing and Reporting roles).

## Parameters

The **deploymentId** parameter is filled in by the PowerShell script.

| Parameter                                 | Description
--------------------------------------------|------------------------------------------------
| sqlServerLogin                            | The name of the administrator account for the newly created Azure SQL server.
| sqlServerPassword                         | The password for the administrator account for Azure SQL server.
| prcMsDeployPackageUrl                     | The blob storage URL of a Web Forms for Marketers Processing Instance Web Deploy package.
| repMsDeployPackageUrl                     | The blob storage URL of a Web Forms for Marketers Reporting Instance Web Deploy package.

## Deploying as part of Sitecore deployment

In order to configure Sitecore deployment parameters to include Web Forms for Marketers:

  * Configure `bootloader` module according to [Modules.md](../../Modules.md)
  * Add the following snippet to the `modules` parameter:

```JSON
{
    "name": "wffm",
    "templateLink": "https://raw.githubusercontent.com/Sitecore/sitecore-azure-quickstart-templates/master/WFFM%208.2.3/xdb/azuredeploy.json",
    "parameters": {
        "prcMsDeployPackageUrl" : "<URL of the WDP file *_prc.scwdp.zip>",
        "repMsDeployPackageUrl" : "<URL of the WDP file *_rep.scwdp.zip>"
    }
}
```
