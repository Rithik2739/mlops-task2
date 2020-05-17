# mlops-task2
Today I'm building a pipline of various jobs in jenkins, this is the second task given in the MLops training under Mr. Vimal Daga.

About the jobs:-

>job1: Pull the code from github automatically whenever a developer push the repository to github.

>job2: Check the type of code pulled and according to it start a container for the code

>job3: test the app is working or not

>job4: send email to the dev if app is not working

>job5: If the container fails then restart it

But first we need to create jenkins image using dockerfile so we can create jenkins container.

No alt text provided for this image
now save this dockerfile and build an image using it after that we just have to launch the container and after that use the base os url with the specified port you can login to jenkins and get to the dashboard.

To built the container use command:

docker run -it --name jenkin -p 8990:8080 imagename
now we create job1:

to get repo from github

No alt text provided for this image


now for job2 it would look like this:

No alt text provided for this image


for the job3 we check if app works or not:

No alt text provided for this image


now as for job4 we send an email if job is working.

But first we have to paste this code in our /etc/sysconfig folder in jenkins

JENKINS_JAVA_OPTIONS="-Djava.awt.headless=true -Dmail.smtp.starttls.enable=true -Dmail.smtp.ssl.protocols=TLSv1.2"

No alt text provided for this image
here we pass SMTP server and gmail credentials.

now command should be like this:

No alt text provided for this image
At last job5 is to check if container is working or not, for this i have used build priodically option.

No alt text provided for this image
With that we are all set but to visualize the flow of jobs we use build pipeline plugin and after using that we can see option to view the pipeline is there.



Now i know that i am late with the task submission due to my pc stopped working and due to lockdown my new laptop's delivery was late and i just started working on this task but i will try my best to improve it.

Thank You.
