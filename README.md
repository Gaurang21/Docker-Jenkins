# Steps to install Jenkins on Docker

1. Pull the Jenkins image from docker repository

```bash
docker pull jenkins/jenkins:lts
```

2. Set Jenkins to run on 8080 port 

```bash
docker run --detach --publish 8080:8080 volume jenkins_home:/var/jenkins_home --name jenkins jenkins/jenkins:lts
```

3. To log into Jenkins first time, Admin Password is required. To get admin password on Docker container use the below command. It will print out the password.

```bash
docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
```

# Create test job on Jenkins - Apache Ivy GitHub Project

1. Create freestyle project and link it to github repository
 ![Screenshot (118)](https://user-images.githubusercontent.com/38041438/118447519-bbb51d00-b6a5-11eb-8fe9-7e2eee2ab4f5.png)
 
 Set target as jar file
 ![Screenshot (120)](https://user-images.githubusercontent.com/38041438/118447711-f4ed8d00-b6a5-11eb-93a6-77bc9a37cdc2.png)

2. Monitor the build on console output
 ![Screenshot (123)](https://user-images.githubusercontent.com/38041438/118447916-2a927600-b6a6-11eb-9ebf-6991a6c0f499.png)
 
 Build Success
 ![Screenshot (125)](https://user-images.githubusercontent.com/38041438/118448116-6a595d80-b6a6-11eb-9438-36f3ced98d14.png)
