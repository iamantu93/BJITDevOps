[Common Training zoom link](https://bjitgroup.zoom.us/j/82240306066?pwd=NW5qdzVDZlEwaFdDNWVpQ3UweS9BZz09)
[DevOps Training materials](https://nextcloud.bjitgroup.com/index.php/s/frKyZnD6oQyL7Fr)
Pass: f5SeRDKd
[Common Training materials](https://nextcloud.bjitgroup.com/index.php/s/ebE4EczzBsyxwfA) 
Pass: 2Lm5rog3
[Java](https://nextcloud.bjitgroup.com/index.php/s/DEo8SsEbPQdkFwB)
Pass: 62r3Z3P8

[Git Slides](https://nextcloud.bjitgroup.com/index.php/s/LieYBcgGKLm4QAX)
Pass: s6Y7XCHZ
[AWS login](https://072262450408.signin.aws.amazon.com/console)

--------------------------------
|     AWS User Credentials     |
--------------------------------
| Account Id: 636981878437     |
| Username: antu.acharjee      |
--------------------------------


# Linux Commands
* ` ssh antu@192.168.56.101 ` 
* `whoami`  **prints current user name**
* `uname -a` **prints computer name with details**
* `hostname` **prints hostname**
* `ip addr` **show ip address and other information**
* `cat /etc/lsb-release` **shows release information**
* `sudo su` **switch user to root**
* `ssh username@ipadress - port` **connect a remote machine via ssh**
* `su - username` **switch to a new user**
* `who` **shows current user**
* `passwd` **updates user's password**
* `pwd` **shows current directory**
* `man command` **shows manual of a command**
* `init 0` **shuts down computer**
* `init 6` **restarts a computer**
* `cat filename` **shows content of a file**
* `ps` **process related information**
* `chmod 764 filename` **change file permission**
* `df` **shows disk space**
* `uptime` **shows how long computer is open**
* `ls` **list files in a directory**
* `cat /etc/passwd` **shows user information**
* `cat /etc/group` **shows group information**
* `chown username:groupname filename` **Changes file ownership**
* `id` **shows user & group information about current user**
* `echo "something"> file` **override content**
* `echo "something" >> file` **does not override content**
* `head -n3 file` **first 3 lines of a file**
* `tail -n3 file` **last 3 lines of a file**
* `sort file.txt` **sort text content of a file**
* `uniq -c file.txt` **display number of unique records in a file**
* `ps aux| grep -i httpd` **search process name and id**
* `kill -9 process_id` **kill a process**


# Files permission in linux
d rwx rwx rw- => file-type owner group others(user without group)
* d directory
* - file
* l link
* r means read 4
* w means write 2
* x means execute 1
* - means no permission 0
* rwx means 4+2+1=7
* rw means 4+2=6

# Hard link vs soft link
* hard link == copy of original file => delete original file no problem
* soft link == actual link of an original file=> delete original file then cannot access link

# Git Commands
`git log` 

`git show commithash-id`   

git checkout commitid 

git checkout branch 
git log filename 

git checkout commit-hashid filname 

git checkout main -f


git reset --soft commithash-id


git status

git log
git diff HEAD 

git commit

git reset --hard commithashid

git log 

git reflog 

git reset HEAD@{8} 

git reset --hard

git log
git show commit-hashid

git add task2.txt

git commit --ammend

git show commitid

git stash

git add 

git diff

git stash 

git stash pop 

git stash list 

git stash

git stash pop

git stash list

git stash pop stash@{1}

git stash

git stash pop stash{2}

git stash clear

git clean -f -n
git clean -f 

# Create a vpc in aws
To create an EC2 instance with NAT, route table, internet gateway (IGW), and subnet in AWS, you can follow these steps:

1. **Sign in to the AWS Management Console**: Go to the AWS website (https://aws.amazon.com/) and sign in to the AWS Management Console using your AWS account credentials.

2. **Open the VPC service**: Once you're signed in, navigate to the VPC (Virtual Private Cloud) service. You can either search for "VPC" in the AWS Management Console search bar or find it under the "Networking & Content Delivery" section.

3. **Create a VPC**: In the VPC Dashboard, click on the "Create VPC" button to create a new VPC. Specify the desired IPv4 CIDR block for the VPC and provide a name tag for identification.

4. **Create a subnet**: After creating the VPC, navigate to the "Subnets" section in the VPC Dashboard. Click on the "Create subnet" button and provide the necessary details such as the VPC you just created, an appropriate CIDR block for the subnet, and a name tag.

5. **Create an internet gateway (IGW)**: In the VPC Dashboard, go to the "Internet Gateways" section and click on the "Create internet gateway" button. Provide a name tag for identification.

6. **Attach the IGW to the VPC**: Select the newly created IGW and click on the "Actions" button, then choose "Attach to VPC." Select the VPC you created earlier and attach the IGW to it.

7. **Create a route table**: Navigate to the "Route Tables" section in the VPC Dashboard and click on the "Create route table" button. Associate the route table with the VPC you created and provide a name tag.

8. **Add a route to the IGW**: Select the newly created route table and click on the "Routes" tab. Click on the "Edit routes" button and add a route with the destination CIDR block of `0.0.0.0/0` and the target set to the IGW you created.

9. **Associate the subnet with the route table**: In the "Subnets" tab of the route table, click on the "Edit subnet associations" button and select the subnet you created. Associate the subnet with the route table.

10. **Create a NAT gateway**: Navigate to the "NAT Gateways" section in the VPC Dashboard and click on the "Create NAT Gateway" button. Select the subnet you created earlier and choose an existing Elastic IP or allocate a new one.

11. **Configure the security groups**: In the EC2 Dashboard, navigate to the "Security Groups" section and create or select a security group that allows inbound and outbound traffic as per your requirements.

12. **Launch the EC2 instance**: Go to the EC2 Dashboard, click on the "Launch Instance" button, and follow the steps mentioned in my previous response about launching an EC2 instance. While launching the instance, make sure to select the appropriate subnet and security group you created.

That's it! You have successfully created an EC2 instance with NAT, route table, internet gateway, and subnet in AWS. The EC2 instance will have outbound internet connectivity through the NAT gateway and will be associated with the specified route table and subnet for proper network configuration.

# Create new user with specific previlage
CREATE USER 'antu'@'localhost' IDENTIFIED BY 'antu1234';
GRANT ALL PRIVILEGES ON antu.* TO 'antu' IDENTIFIED BY 'antu1234' WITH GRANT OPTION;
FLUSH PRIVILEGES;
# Connecting with host name
mysql -h antudb1.c5tsce7xtv8b.eu-west-3.rds.amazonaws.com -u antu -p
# Create Load balancer
* at least one plublic ec2
* multiple private ec2
* add private ones to target group
* add listener rule
* select target group while creating LB

# Agile Menifesto
The Agile Manifesto is a set of guiding principles for software development that emphasizes flexibility, collaboration, and adaptability. It was created in 2001 by a group of software developers who wanted to find a better way to deliver high-quality software in a more efficient and responsive manner. The Agile Manifesto consists of four core values and twelve principles:

Agile Manifesto Values:
1. Individuals and interactions over processes and tools: This value emphasizes the importance of people and their interactions in the software development process, prioritizing effective communication and collaboration over relying solely on tools and processes.

2. Working software over comprehensive documentation: This value highlights the importance of delivering functional software that meets the customer's needs rather than focusing excessively on extensive documentation that may not add direct value to the end product.

3. Customer collaboration over contract negotiation: This value promotes the active involvement of the customer throughout the development process, encouraging collaboration, feedback, and continuous interaction to ensure that the software meets the customer's requirements.

4. Responding to change over following a plan: This value recognizes the dynamic nature of software development and the need to be adaptable to changes in requirements or priorities. It encourages teams to embrace change and adjust their plans accordingly to deliver the best possible outcomes.

Agile Manifesto Principles:
1. Our highest priority is to satisfy the customer through early and continuous delivery of valuable software.
2. Welcome changing requirements, even late in development. Agile processes harness change for the customer's competitive advantage.
3. Deliver working software frequently, with a preference for shorter timescales.
4. Business people and developers must work together daily throughout the project.
5. Build projects around motivated individuals. Give them the environment and support they need, and trust them to get the job done.
6. The most efficient and effective method of conveying information to and within a development team is face-to-face conversation.
7. Working software is the primary measure of progress.
8. Agile processes promote sustainable development. The sponsors, developers, and users should be able to maintain a constant pace indefinitely.
9. Continuous attention to technical excellence and good design enhances agility.
10. Simplicity--the art of maximizing the amount of work not done--is essential.
11. The best architectures, requirements, and designs emerge from self-organizing teams.
12. At regular intervals, the team reflects on how to become more effective, then tunes and adjusts its behavior accordingly.

These values and principles serve as a foundation for Agile methodologies such as Scrum, Kanban, and Extreme Programming (XP), which provide specific frameworks and practices for implementing Agile software development.

# Scrum framework
The Scrum framework is an agile project management methodology designed to help teams efficiently deliver high-quality products. It emphasizes collaboration, flexibility, and iterative development. Scrum is widely used in software development but can be applied to other complex projects as well. Here are some key aspects of the Scrum framework:

1. Roles: Scrum defines three primary roles:
   - Product Owner: Represents the stakeholders, defines the product vision, prioritizes the product backlog, and ensures the team is building the right product.
   - Scrum Master: Facilitates the Scrum process, removes obstacles, and helps the team to improve its practices.
   - Development Team: A self-organizing cross-functional group responsible for delivering a potentially releasable product increment at the end of each sprint.

2. Artifacts:
   - Product Backlog: A prioritized list of all desired product features, enhancements, and bug fixes. It is maintained by the Product Owner and constantly refined.
   - Sprint Backlog: A subset of the product backlog items selected for a specific sprint. It represents the work the development team commits to completing during the sprint.
   - Increment: The sum of all completed product backlog items at the end of a sprint. It must be in a potentially releasable state, meeting the team's definition of "Done."

3. Events:
   - Sprint: A time-boxed period (usually 1-4 weeks) in which the development team creates a releasable increment of the product. It starts with sprint planning and ends with a sprint review and retrospective.
   - Sprint Planning: A collaborative session where the team selects items from the product backlog and plans the work for the upcoming sprint.
   - Daily Scrum: A short daily meeting for the development team to synchronize activities, discuss progress, and identify any obstacles.
   - Sprint Review: A meeting held at the end of each sprint to inspect the increment and gather feedback from stakeholders.
   - Sprint Retrospective: A session where the team reflects on its process, identifies areas for improvement, and plans experiments to enhance future sprints.

4. Principles:
   - Empirical Process Control: Scrum is based on transparency, inspection, and adaptation, enabling teams to make informed decisions based on real-world observations.
   - Self-Organization: The development team organizes itself and determines how to accomplish the work, promoting ownership, creativity, and collaboration.
   - Collaboration: Scrum emphasizes open communication and collaboration between team members and stakeholders to achieve the best outcomes.

Scrum provides a framework that encourages flexibility and responsiveness to change, enabling teams to adapt quickly to evolving requirements and deliver value iteratively throughout the project.


# Docker Cheat sheet

