# Ansiblewesttigers

This repo is a place to have demo playbooks for our Customer to leverage during POC's and trials.

Format: 

Playbooks should define blank Varables that are needed for the Playbook to run successfully. These variable should be passed to the playbook from Tower Surveys or extra Vars in templates.  Any variable that is pulled from Ansible facts should be commented as such

Example.
vars:  /n
    az_rgname: ''
    location: ''
    customer: ''
    AZURE_CLIENT_ID: ''        # passed from Ansible Tower Credentials 
    AZURE_SECRET: ''           # passed from Ansible Tower Credentials
    AZURE_SUBSCRIPTION_ID: ''  # passed from Ansible Tower Credentials
    AZURE_TENANT: ''           # passed from Ansible Tower Credentials 
