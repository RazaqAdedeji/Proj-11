## PROJECT 11: Ansible – Automate Project 7 to 10


1. INSTALL AND CONFIGURE ANSIBLE ON EC2 INSTANCE

'sudo apt update'

'sudo apt install ansible'

- Check your Ansible version by running ansible --version

![alt text](images/1%20ansible%20vers.png)

- Configure Jenkins build job to save your repository content every time you change it – this will solidify your Jenkins configuration skills acquired in Project 9.

- Test your setup by making some change in README.MD file in master branch and make sure that builds starts automatically and Jenkins saves the files (build artifacts) in following folder

![alt text](images/3%20Test%20with%20Readme%20file.png)

![alt text](images/2%20jenkins%20FB.png)

'ls /var/lib/jenkins/jobs/ansible/builds/<build_number>/archive/'

![alt text](images/4%20ls%20%3Avar%3Alib.png)

2. Step 2 – Prepare your development environment using Visual Studio Code

![alt text](images/5%20git%20clone%20repo.png)

3. BEGIN ANSIBLE DEVELOPMENT

- In your ansible-config-mgt GitHub repository, create a new branch that will be used for development of a new feature.

![alt text](images/6%20create%20a%20branch.png)

- Create a directory and name it playbooks – it will be used to store all your playbook files.

- Create a directory and name it inventory – it will be used to keep your hosts organised.

- Within the playbooks folder, create your first playbook, and name it common.yml

- Within the inventory folder, create an inventory file (.yml) for each environment (Development, Staging Testing and Production) dev, staging, uat, and prod respectively.

![alt text](images/7%20inventory%20yaml%20.png)

4. Set up an Ansible Inventory

'eval `ssh-agent -s`'

'ssh-add <path-to-private-key>'

'ssh -A ubuntu@public-ip'

![alt text](images/8%20ssh%20agent.png)

- Update your inventory/dev.yml file with this snippet of code:

5. CREATE A COMMON PLAYBOOK

- Update your playbooks/common.yml file with following code:

![alt text](images/9%20edit%20playbooks.png)

6. Update GIT with the latest code

- Commit your code into GitHub:

![alt text](images//10%20git%20commit%20n%20push.png)

- Create a Pull request (PR)

![alt text](images/11%20git%20pull%20n%20merge.png)

- Head back on your terminal, checkout from the feature branch into the master, and pull down the latest changes.

![alt text](images/12%20jenkin%20trigger.png)

- Once your code changes appear in master branch – Jenkins will do its job and save all the files (build artifacts) to /var/lib/jenkins/jobs/ansible/builds/<build_number>/archive/ directory on Jenkins-Ansible server.

![alt text](images/13%20ls%20var%3Alib.png)

7. Run first Ansible test

'cd ansible-config-mgt'

'ansible-playbook -i inventory/dev.yml playbooks/common.yml'

![alt text](images/14%20playbook%20execute.png)

![alt text](images/15.png)

![alt text](images/16.png)

![alt text](images/17.png)