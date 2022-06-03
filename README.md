# Cisco TAC SecureX Automated Troubleshooting
This repository provides workflows that can be run in Cisco SecureX. The primary purpose of the workflows in this repository are for troubleshooting issues with Cisco Products.  
Note: This project is still in the PoC phase and is not currently recommended for use unless directly advised by Cisco TAC.

# Quickstart
The recommended basics steps to get started are:
1. [Add this github repository to your SecureX account](#create-the-github-repository-in-securex)
2. [Import the desired workflow](#import-workflow)
3. [Create a target for the device the workflow needs to be run on](#create-a-target)
4. [Run the workflow](#run-a-workflow)
5. [View the Result Report](#viewing-results)

# Importing a Workflow
In order to use the workflows you must first import them to your SecureX workflows.

## Import  from Github
### Create the Github repository in SecureX
The recommended way to import the workflows is to add this github repository to your SecureX account.  
See [the documentation for how to add a Github repo](https://ciscosecurity.github.io/sxo-05-security-workflows/configuration/#creating-the-git-repository-for-workflows).  
Use the following options when creating the Github repo:

REST API Repository: `api.github.com/repos/CiscoDevNet/tac-securex-automated-troubleshooting`  
Branch: `main`  
Code Path: `Workflows`

### Import workflow
Once you've added this github repository you should see it in the dropdown options when you click the `import` button on the main orchestration page.  
See [the documentation for how to import from a Github Repository](https://ciscosecurity.github.io/sxo-05-security-workflows/importing#importing-from-github) for more info.

# Create a target
You will need to create a target for the device(s) you want to run the workflows on.  
All workflows use either `SSH` or `HTTPS` to connect to the device, so you need to make sure that SecureX is able to reach them.  
If your device is unable to be accessed directly from SecureX (likely) then you would need to set up a [SecureX orchestration remote](https://ciscosecurity.github.io/sxo-05-security-workflows/remote/_) first which is able to talk to your on-prem devices.  
Disclaimer: The SecureX remote currently only supports HTTPS, and most of the workflows in this will require SSH.
If your devices are on prem then this may not be practical for you to use until there is an SSH remote available.

## Settings for Terminal Endpoint target (SSH)
When creating the target for workflows that require SSH you should use the following settings:  
Target Type: `Terminal Endpoint`  
For `Account Keys` you should use `Terminal Password-Based Credentials` and use a user which has expert mode access. 
You should make sure to fill out the `Admin (Enable/Sudo) Password` with the password for the user as some workflows may require root access.  
Under the `Terminal Interaction Patterns (regex)` section use the following settings:  
Prompt: `>|\$|#`  
for `Additional Succeeded Prompts ( Admin Prompt, etc. )` you should add 2 prompts:  
`\$`  
`#`

# Run a Workflow
Once you have the target created and the workflow imported, you can then run it.    
To run the workflow you can click the `...` from the card (on the main workflows page) and then select `Run` or you can open the workflow and click `Run` at the top right.  
All of the workflows will prompt to select a target at start up.

# Viewing Results
Results are output from the workflows as the `O_report_markdown` variable. You can copy and paste this into a markdown viewer in an IDE or online to get a pretty view. You can use something like
https://dillinger.io/ (not a Cisco owned app).

# List of Available Workflows

## [Secure Firewall Disk Space Checker](Workflows/Secure-firewall-Disk-Space-Checker__definition_workflow_01WOLLDJ04UHR4kvLNe1Be3NmMWIjNAt2eq)

