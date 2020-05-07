# devopstask
## myblog
### Task about integration of jenkins with GitHub.

**IN GitHub**
 *  Create one repository without any branches.

**In Windows** 
 * Created a local repository. 
 * In this repository two branches are created. 
   * Master 
   * Dev1 
   ```javascript
   git init 
   cat > a.txt
   git add.
   git commit. -m "first"
   git branch dev1 
   git remote -v
   git remote add origin URL
   git push -u origin master
   git push -u origin  dev1
   ```
   
   
**this data is updated in github in master  and dev1 branch*

**In Jenkins**
  * job1 created using poll scm trigger. 
    * this job keeps on checking dev1 branch. if there's anything updates it automatically send this to testing operating system.
    * this job deploys the data to testing operating system.
  
  * allow root to run any command to give jenkins power
  ```javascript
  gedit /etc/sudoers
  ```
  ```javascript
  sudo cp -v -r -f /lwweb

  if sudo docker ps|grep testmyos web
  then
  echo "already running"
  else 
  sudo docker run -d -t -i -p 8082:80 -v /lwweb:/usr/localapache/htdocs/--name testmyos1 httpd
  fi
  ```
    
  * job2 created to keep on checking the main branch.
    * this job send the data to main production team. 
    
  * job 3 created to verify the testing data that was given by job1. for this QAT team is connected to remote url.
     * after testing succeeded, QAT team merge this data to master branch of github.
     
   _**after master updated then job2 is automatically triggered**_
      * after job2 created successfully they send data to production team. 
     
  _**Production team send this data to webserver using tunnel by exposing  where client can connect**_ 
  
  **in the job2 execute shell**
  ```javascript
  if sudo docker ps|grep runmyos web
  then
  echo "already running"
  else 
  sudo docker run -d -t -i -p 8082:80 -v /lwweb:/usr/localapache/htdocs/--name runmyos1 httpd
  fi
  ```
  
  
     
    



  




