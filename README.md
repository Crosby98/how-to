# How to build core/engage on windows 10

1. Install Apache Ant - [link to Ant](https://ant.apache.org/bindownload.cgi) and add to *PATH_VARIABLES*, you will need two path variables to add: 
   * ANT_HOME = path to ant folder. For example (C:\Users\user\Desktop\apache-ant-1.10.7)
   * ANT_OPTS = -Xms256M -Xmx512M -Dfile.encoding=UTF8.
2. Also add this PATH VARIABLES:
   * IVY_USER=*your IBM intranet username* **in ALL LOWERCASE NOT UPPERCASE**
   * IVY_PASSWORD=*your API key for IBM TaaS Artifactor*, created earlier in Artifactory
3. Create folder with name ***core***
4. Clone Git repo ca-branch-configurations as ~/branch-configurations  e.g. in ***core*** directory run git clone **git@github.com:aipoweredmarketer/ca-branch-configurations.git**
5. Clone Git repo ca-build-common as ~/build-common  e.g in ***core*** directory run git clone **git@github.com:aipoweredmarketer/ca-build-common.git**
6. You will also need to set some environment variables: 
   * CM_HOME=(path to ***core*** folder) e.g (CM_HOME=C:\DevEnvironment\borisov\borisov_engage)
   * BUILD_COMMON_RELEASE=master.
7. Clone Git repo for any Campaign project which uses Ant (build.xml file) and move to the directory of the project.
8. You should now be able to run **'ant clean resolve make'** to build the Campaign project.

*Notes:* *you alse need to have java environment set, and be able clone reposiroties via ssh*
# How to build core/engage on Amazon WorkSpaces
1. Install Apache Ant - [link to Ant](https://ant.apache.org/bindownload.cgi). 
2. Install openjdk 8 (run command in cmd)
```sh
  $ sudo yum install java-1.8.0-openjdk-devel
```
3. Create folder with name ***core***
4. Clone Git repo ca-branch-configurations as ~/branch-configurations  e.g. in ***core*** directory run git clone **git@github.com:aipoweredmarketer/ca-branch-configurations.git**
5. Clone Git repo ca-build-common as ~/build-common  e.g in ***core*** directory run git clone **git@github.com:aipoweredmarketer/ca-build-common.git**
6. You will need to find file .bashrc in your home directory (hidden file, press ctrl+H to see hidden files) and add path_variables here, see example below: 
```sh
JAVA_HOME=~/tools/java/jdk8 (path to jdk)
ANT_HOME=~/tools/apache-ant-1.10.7 (path to ant folder)
ANT_OPTS="-Xms256M -Xmx512M"
export ANT_HOME ANT_OPTS JAVA_HOME PATH
export PATH=${ANT_HOME}/bin:${JAVA_HOME}/bin:${PATH}
export CM_HOME=~/workspace/core (path to core folder)
export BUILD_COMMON_RELEASE=master
export IVY_USER=(your IBM intranet username in ALL LOWERCASE NOT UPPERCASE)
export IVY_PASSWORD=(your API key for IBM TaaS Artifactor, created earlier in Artifactory)
```
7. Clone to ***core*** directory any Campaign project which uses Ant (build.xml file) and run ***'ant clean resolve make'*** command in project folder.
 
*Notes:* *you alse need to be able clone reposiroties via ssh*
