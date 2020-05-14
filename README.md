# Jenkins Automation Project
PROBLEM STATEMENT:

1. Create container image that has Jenkins installed using Dockerfile

2. When we launch this image, it should automatically start Jenkins service in the container.

3. Create a job chain of job1, job2, job3 and job4 using build pipeline plugin in Jenkins

4. Job1 : Pull the Github repo automatically when some developers push repo to Github.

5. Job2 : By looking at the code or program file, Jenkins should automatically start the respective language interpreter install image container to deploy code ( eg. If code is of PHP, then Jenkins should start the container that has PHP already installed ).

6. Job3 : Test your app if it is working or not and if app is not working , then send email to developer with error messages.

7. Create one extra job - job4 for monitoring : If container where app is running. fails due to any reason then this job should automatically start the container again.

Steps:

1. Create docker image that has Jenkins installed using Dockerfile

![](https://github.com/SuhaniArora/Jenkins_container/blob/master/jenkin_docker/Dockerfile.png)

2. Build the docker image using the command - docker build -t jenkins:v1 .

![](https://github.com/SuhaniArora/Jenkins_container/blob/master/jenkin_docker/docker_run.png)

3. After building and running the image check on which port your container is running and start jenkins.

4. Create First job - j1 - this job will copy the cod efrom github to the directory specified.

![](https://github.com/SuhaniArora/Jenkins_container/blob/master/jenkin_docker/1_1.png)

![](https://github.com/SuhaniArora/Jenkins_container/blob/master/jenkin_docker/1_2.png)

![](https://github.com/SuhaniArora/Jenkins_container/blob/master/jenkin_docker/1_3.png)

5. Now create second job that will run aftter first one is successfully executed.

![](https://github.com/SuhaniArora/Jenkins_container/blob/master/jenkin_docker/2_1.png)

![](https://github.com/SuhaniArora/Jenkins_container/blob/master/jenkin_docker/2_2.png)

![](https://github.com/SuhaniArora/Jenkins_container/blob/master/jenkin_docker/2_3.png)

6. Create next job - j3 that wil be checking the code and will mail to the developer if thecode fails

![](https://github.com/SuhaniArora/Jenkins_container/blob/master/jenkin_docker/3_1.png)

![](https://github.com/SuhaniArora/Jenkins_container/blob/master/jenkin_docker/3_2.png)

![](https://github.com/SuhaniArora/Jenkins_container/blob/master/jenkin_docker/3_3.png)

Before setting the post-build instal Email plugin and configure the following settings in Manage Jenkins --> configure System.

![](https://github.com/SuhaniArora/Jenkins_container/blob/master/jenkin_docker/3_4.png)

![](https://github.com/SuhaniArora/Jenkins_container/blob/master/jenkin_docker/3_5.png)

![](https://github.com/SuhaniArora/Jenkins_container/blob/master/jenkin_docker/3_6.png)

The build pipeline view for the above jobs is :

![](https://github.com/SuhaniArora/Jenkins_container/blob/master/jenkin_docker/build_view.png)

7. Now build a job - j4 fot testing the the containers are running or not.

![](https://github.com/SuhaniArora/Jenkins_container/blob/master/jenkin_docker/4_1.png)

![](https://github.com/SuhaniArora/Jenkins_container/blob/master/jenkin_docker/4_2.png)

The docker containers that are running are:

![](https://github.com/SuhaniArora/Jenkins_container/blob/master/jenkin_docker/Docker_containers.png)
