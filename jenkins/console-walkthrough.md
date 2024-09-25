# Below is the Jenkins Console Walkthrough for better understanding each feature.


### I. Login Screen
In this page we need to entire credentials and login to the Jenkins dashboard. Default Jenkins port is 8080. 

Learning: As we are aware on restart of EC2, the public IP changes, so our Jenkins URL also changes. Thus, the Jenkins becomes slow. To resolve this issue we need to replace the old public ip with the new one in 'System Configuration > System'.

<img width="896" alt="image" src="https://github.com/user-attachments/assets/056d3ba3-f40c-4c1d-8c43-53046253313d">

### II. Home Page

When we login we are redirected to the dashboard of the Jenkins. Here we see below stuffs - 
1. In Top Panel where we see which user is logged in(username)
2. In Left Panel we see a) 'New Item' link for creating new pipeline. b) 'Manage Jenkins' Link to do admin related changes.
3. In Center page, we see a) 'Start building your software project' notes we can start creating our pipeline from there as well. b) 'Set up a distributed build', from here we can add nodes for managing traffic among multiple instances.

<img width="944" alt="image" src="https://github.com/user-attachments/assets/184784f7-a009-4d63-97b5-34daae6ffe27">

