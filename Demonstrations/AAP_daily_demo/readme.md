# Ansible Automation Platform (AAP) Daily Demo
### AAP Daily Demo requirements  
    -   An Amazon Web Services account
    -   Your ssh public key must be installed in AWS management console.  The create_instance.yml is expecting a key named {{ vpc_name }}-ssh-key
### AAP Daily Demo build up
**The AAP Daily Demo is an AAP workflow**  
1. [The create_vpc.yml is the first playbook in the workflow.](https://github.com/redawg/Ansiblewesttigers/blob/master/Demonstrations/AAP_daily_demo/create_vpc.yml "create_vpc.yml")  
        ***Template variable examples***  
        ---  
        vpc_name: zigfreed  
        vpc_cidr: 172.16.1.0/24  
        region: us-west-2  
        user_name: hercules  
        alwaysup: false  
        deleteby: hercules
2. [The create_instance.yml is the second playbook in the workflow.](https://github.com/redawg/Ansiblewesttigers/blob/master/Demonstrations/AAP_daily_demo/create_instance.yml "create_instance.yml")  
        ***Template variable examples***  
        ---  
        vpc_name: zigfreed  
        user_name: hercules  
        subnet_name: "{{vpc_name}}_Subnet"  
        image: ami-0d6d43816a7c20dcf  
        count: 1  
        region: us-west-2  
        assign_public_ip: yes  
        alwaysup: false  
        instance_type: t2.micro    
3. [The aws_inventory_sync.yml is the third playbook in the workflow.](https://github.com/redawg/Ansiblewesttigers/blob/master/Demonstrations/AAP_daily_demo/aws_inventory_sync.yml "aws_inventory_sync.yml")  
        ***Template survey variable examples***  
        ---  
        username:    
        password:  
        tower_url:  
        inventory_id:  

        ****Special Note****
        The inventory is a dynamic inventory

### AAP Daily Demo tear down  
