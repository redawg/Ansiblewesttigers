# Ansible Automation Platform (AAP) Daily Demo
### AAP Daily Demo requirements  
    -   An Amazon Web Services account
    -   Your ssh public key must be installed in AWS management console.  The create_instance.yml is expecting a key named {{ vpc_name }}-ssh-key
### AAP Daily Demo build up
**The AAP Daily Demo is an AAP workflow**  
    1. [The create_vpc.yml is the first playbook in the workflow](https://github.com/redawg/Ansiblewesttigers/blob/master/Demonstrations/AAP_daily_demo/create_vpc.yml "create_vpc.yml")  
        
        <sup>Template variable examples</sup>
        ---  
        vpc_name: zigfreed  
        vpc_cidr: 172.16.1.0/24  
        region: us-west-2  
        user_name: eames  
        alwaysup: false  
        deleteby: eames  

    2. [The create_instance.yml is the second playbook in the workflow](https://github.com/redawg/Ansiblewesttigers/blob/master/Demonstrations/AAP_daily_demo/create_instance.yml "create_instance.yml")  
        
        <sup>Template variable examples</sup>

### AAP Daily Demo tear down  
