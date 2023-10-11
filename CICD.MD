### CICD Process

![alt text](images/ci.png)

![alt text](images/cd.png)

#### Steps:
1. Make sure roboshop-infra-dev is created.

    * VPC
    * Firewalls
    * VPN
    * MongoDB
    * Application ALB
2. Install Open VPN. We need this VPN to access private servers of Roboshop. We have userdata implemented to install openvpn already. You can see one .ovpn file in /root folder. Access with sudo.
3. Make sure you have all the configuration exist.
4. Make sure you have Jenkins, atleast one agent, nexus are running.
5. Developer continuously pushes the code to feature branches.
6. DevOps Engineer should configure CICD pipelines.
7. CD pipeline is running as downstream job, if CI is success, CD would be called automatically. CI job should send the app version to CD job.
8. Deployment pipeline is integrated with AWS through Terraform.
    * Make sure terraform is installed in agent.
    * Make sure aws configure is done in agent.
    * We will provision one EC2 instance.
    * We will run remote provisioner job, This job installs ansible in EC2, pulls ansible playbooks, run particular component(for example catalogue) in VM.
    * Once playbook run successfully, we will stop the instance and take AMI out of it.
    * We will delete the instance.
    * We will input AMI to the launch template. Target groups, ASG should be configured.
