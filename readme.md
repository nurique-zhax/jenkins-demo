**Tomcat / Jenkins**

-   This task contains “surface” setting Tomcat Server on Virtual Machine and integrating with Jenkins

**Table of Contents**

-   Step 1: Virtual Machine
-   Step 2: Adding SSH key in GitHub and Jenkins
-   Step 3: Start and Enable Tomcat
-   Step 4: Configure Tomcat for Jenkins
-   Step 5: Connect Jenkins to Tomcat
-   Step 6: Testing the Integration

**Technologies Used:**

-   Oracle VirtualBox (RedHat CentOs 9)
-   Tomcat
-   Jenkins

**Step 1: Virtual Machine**

For this task, I used Oracle VirtualBox, with the CentOs 9:

![11376a99e00411479da62cd6a8f4e062](https://github.com/user-attachments/assets/5f0338e6-a855-4d44-996c-a58e72891f11)


**Step 2: Adding SSH key in GitHub and Jenkins**

We should add SSH key in GitHub and Jenkins, because we need to Jenkins see the commits that we add in our remote repository. It will trigger Jenkins to start a build

GitHub:

![8992e08ec55bca35c2a9efe0396a20b1](https://github.com/user-attachments/assets/1f9d05eb-c67e-4c09-a4ab-011cc453f4c5)


Jenkins:

![578c27fea80e13253d796bf29fa32c6c](https://github.com/user-attachments/assets/0a2a9fda-c626-459d-b123-1e867da3ad4c)


**Step 3: Start and Enable Tomcat**:

Enabling Tomcat and verifying that Tomcat is running

![ab600e3bd142c36b4583becfed3b8cac](https://github.com/user-attachments/assets/73035f85-bcd7-4c26-a1b7-09e30bc425f4)


![a6a6b5f320e7315342ed202d3f384f16](https://github.com/user-attachments/assets/2ab416e8-632f-4204-bcb9-0fa5c412ea39)


**Step 4: Configure Tomcat for Jenkins**

We should create a user for Jenkins Deployment, to do that we need edit the “tomcat-users.xml” with “*sudo nano /opt/tomcat/conf/tomcat-users.xml”* command

![7fb549c4022989b532ac581140cfb814](https://github.com/user-attachments/assets/cd3276a9-c77b-4527-8018-45c1daf8f1d2)


After that, we need to add this user credentials to Jenkins:

![48fb669eb27a5a85856d24fa691904f3](https://github.com/user-attachments/assets/dfa65a57-f535-4522-b633-962c6d84dc96)


**Step 5: Connect Jenkins to Tomcat**

![0d17a1c4f4aa52d14c3aec221999a67a](https://github.com/user-attachments/assets/5e4d5bcf-983f-4945-a054-05424b7460f4)


Now we need to install “Deploy to Container” Plugin in Jenkins, after that we should configure Tomcat container that runs on VirtualMachine to Jenkins

**Step 6: Testing the Integration**

Now after all preparation, we can check that after our commit Jenkins will trigger the build and will deploy it to the Tomcat Server on VM

![74b831ac6e8c9df6d69be7dbbf14c1ab](https://github.com/user-attachments/assets/32f063fb-6683-4453-874f-c36e6f7491c9)


Tomcat:  
![68330eb00bddbe61e65a1cab79cf5243](https://github.com/user-attachments/assets/4fd15997-6397-422b-b928-9375e563e5a4)
