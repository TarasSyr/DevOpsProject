
Creating ec2 instance on AWS

![Aspose Words 3e80664f-526d-4c76-8f35-b7c041c321d7 007](https://user-images.githubusercontent.com/123966763/220108033-f1504ca1-bb41-4343-862a-11d26743f4b9.png)
![Aspose Words 3e80664f-526d-4c76-8f35-b7c041c321d7 008](https://user-images.githubusercontent.com/123966763/220108094-ed4a3605-045d-4893-a5f6-54fc4e92ebeb.png)

Editing inbound security group so i can connect via port 8080(default Jenkins port)

![Aspose Words 3e80664f-526d-4c76-8f35-b7c041c321d7 010](https://user-images.githubusercontent.com/123966763/220108395-50ba1c5c-28f0-40a2-80b6-ad3848fec475.png)

Downloading and installing Jenkins

![Aspose Words 3e80664f-526d-4c76-8f35-b7c041c321d7 004](https://user-images.githubusercontent.com/123966763/220107442-27aefd45-754e-4de7-9d81-efcf24f65814.png)

![Aspose Words 3e80664f-526d-4c76-8f35-b7c041c321d7 001](https://user-images.githubusercontent.com/123966763/220107209-5b524c5e-a367-432d-91fe-410eda661771.png)
![Aspose Words 3e80664f-526d-4c76-8f35-b7c041c321d7 002](https://user-images.githubusercontent.com/123966763/220107324-6960b4eb-f61a-4225-bedf-a70a88a63ec8.png)
![Aspose Words 3e80664f-526d-4c76-8f35-b7c041c321d7 003](https://user-images.githubusercontent.com/123966763/220107375-311121fa-c3cf-4cc5-a99c-6ab25b137d1e.png)

Creating key pair for Jenkins

![Aspose Words 3e80664f-526d-4c76-8f35-b7c041c321d7 005](https://user-images.githubusercontent.com/123966763/220107562-0febc418-e4a6-4a9b-a6d8-0ac40eeac548.png)

Saving key pair on computer

![Aspose Words 3e80664f-526d-4c76-8f35-b7c041c321d7 006](https://user-images.githubusercontent.com/123966763/220107671-98954f89-83b1-45c9-be36-d488ff229ac7.png)

Configuring slave(ec2) url

![Aspose Words 3e80664f-526d-4c76-8f35-b7c041c321d7 011](https://user-images.githubusercontent.com/123966763/220108512-a02651e7-452b-4a3d-820c-909bc5dfe2fd.png)

Installing Amazon plugins on Jenkins

![image](https://user-images.githubusercontent.com/123966763/220109463-53700a3f-ee6f-4571-aab8-72ca716e3eed.png)
![image](https://user-images.githubusercontent.com/123966763/220109570-5008b606-1e00-4c55-b7e5-aeb2c3e5c81e.png)

Configuring clouds(slaves) on Jenkins

![image](https://user-images.githubusercontent.com/123966763/220109694-a6d5ee0e-c38d-41fc-a75e-ad519260dcbc.png)

Installing apache server in EC2

![image](https://user-images.githubusercontent.com/123966763/220109895-5d7deb79-971c-4069-8d58-28ff249cd53c.png)

Default test apache page

![image](https://user-images.githubusercontent.com/123966763/220110037-7e0ac9a3-19a8-4af1-98df-52cdacc36993.png)

Making a simple Jenkins job to check if it's working

![image](https://user-images.githubusercontent.com/123966763/220110268-11e415f4-23eb-4527-bab4-1f6c712a1fb7.png)

Github repository

![image](https://user-images.githubusercontent.com/123966763/220110866-44c683f1-b973-49a3-9c1e-5200aa1f57ea.png)


It's working(file index.html is on the GitHub repository)

![image](https://user-images.githubusercontent.com/123966763/220110460-2aeda7f5-5a17-4e03-8b92-4907b47faef9.png)

Now we do a simple copying from one directory to other via jenkins build steps(execute shell)
But we have a problem

![image](https://user-images.githubusercontent.com/123966763/220111290-4eab1b3b-da87-4728-9557-3a8ebcb4a22b.png)

AWS wont let user with "jenkins" username access some directories and copy them. The solution is to change sudo rules.
Changing sudoers file with command **visudo -f /etc/sudoers**

![image](https://user-images.githubusercontent.com/123966763/220111573-4bd2d9f0-6a46-4b1a-8179-142ba6efc77d.png)

Adding **jenkins ALL= NOPASSWD: ALL**

![image](https://user-images.githubusercontent.com/123966763/220111731-f751ec48-1873-42b6-bbf2-3ca523d05d3c.png)

After that save and exit: **wq**
After that we go on Jenkins page and press build now. And build is successful 

![image](https://user-images.githubusercontent.com/123966763/220111887-88512bde-64c2-4036-8487-8b0ce9a962f6.png)

Test page

![image](https://user-images.githubusercontent.com/123966763/220111955-921efd3e-45ab-40a6-b2ec-8f8a155900cf.png)




