Steps to deploying the php webapp to ec2 instance using github actions 

Step 1: Start an ec2 machine and then install the basic dependies in the machine by doing ssh into it

step 2: add a .github/workflows/test.yml file in your github repository, here all your code related to your github actions will be stored

step 3: You have to copy your access keys and your secret key to the secrets of your repository, so that github can access your aws account to make the deployements

step 4: you also have to tell github on which ec2 you want to make a deployement i.e. add your target ec2 as a runner in your test.yml runs on section.

    step 4.1 to add your target ec2 as a runner go to the settings > actions > runner > new self-hosted runner.

    step 4.2 if you are deploying on linux then select linux and follow the steps in your ec2 instane by doing ssh

step 5: once you install runner in your ec2 you have to make it as a service as if you dont do it then you have to manually start your runner service everytime you will make a deployement, follow these steps to make runner as a service so everytime when the machine will start it will automatically start the runner.

    step 5.1 Stop the self-hosted runner application if it is currently running.

    step 5.2 Install the service with the following command: sudo ./svc.sh install
    
    step 5.3 Start the service with the following command: sudo ./svc.sh start

now you are good to go, copy the test.yml file in this repository and enjoy the CI/CD deployement.