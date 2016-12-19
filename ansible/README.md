Devops Code
=========

This dierectory contains ansible code for infrastructure provisioning and management.

Requirements
------------

To run this code you will need to have ansible installed on your machine, or if you using a CI tools like jenkins your should have the related plugins installed on the system.


How to use
----------------

Including an example of how to use this code
    
    Clone the repository in a directory and cd to the directory.
    Go to ansible/playbook and run below command
    
     ansible-playbook -i ../hosts tomcat_install.yml -k  --ask-vault-pass

How to on AWS
-------


Author Information
------------------

Kumar Shantanu.
