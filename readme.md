**Tomcat / Jenkins**

-   This task contains “surface” setting Tomcat Server on Virtual Machine and integrating with Jenkins

**Table of Contents**

-   Step 1: Virtual Machine
-   Step 2: Adding SSH key in GitHub and Jenkins
-   Step 3: Start and Enable Tomcat
-   Step 4: Configure Tomcat for Jenkins
-   Step 5: Connect Jenkins to Tomcat
-   Step 6: Testing the Integration
-   Conclusion

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

![](media/8992e08ec55bca35c2a9efe0396a20b1.png)

Jenkins:

![](media/578c27fea80e13253d796bf29fa32c6c.png)

**Step 3: Start and Enable Tomcat**:

Enabling Tomcat and verifying that Tomcat is running

![A screen shot of a computer program Description automatically generated](media/ab600e3bd142c36b4583becfed3b8cac.png)

![A screenshot of a computer Description automatically generated](media/a6a6b5f320e7315342ed202d3f384f16.png)

**Step 4: Configure Tomcat for Jenkins**

We should create a user for Jenkins Deployment, to do that we need edit the “tomcat-users.xml” with “*sudo nano /opt/tomcat/conf/tomcat-users.xml”* command

![A screenshot of a computer Description automatically generated](media/7fb549c4022989b532ac581140cfb814.png)

After that, we need to add this user credentials to Jenkins:

![](media/48fb669eb27a5a85856d24fa691904f3.png)

**Step 5: Connect Jenkins to Tomcat**

![A white paper with lines Description automatically generated](media/0d17a1c4f4aa52d14c3aec221999a67a.png)

Now we need to install “Deploy to Container” Plugin in Jenkins, after that we should configure Tomcat container that runs on VirtualMachine to Jenkins

**Step 6: Testing the Integration**

Now after all preparation, we can check that after our commit Jenkins will trigger the build and will deploy it to the Tomcat Server on VM

![](media/74b831ac6e8c9df6d69be7dbbf14c1ab.png)

Tomcat:  
![A screenshot of a computer Description automatically generated](media/68330eb00bddbe61e65a1cab79cf5243.png)
