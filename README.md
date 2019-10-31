# How to build core/engage on windows 10

1. Install Apache Ant - [link to Ant](https://ant.apache.org/bindownload.cgi) and add to PATH_VARIABLES, you will need two path variables to add: 
   * ANT_HOME = path to ant folder. For example (C:\Users\user\Desktop\apache-ant-1.10.7)
   * ANT_OPTS = -Xms256M -Xmx512M -Dfile.encoding=UTF8.
2. Also add this PATH VARIABLES:
   * IVY_USER=*your IBM intranet username* **in ALL LOWERCASE NOT UPPERCASE**
   * IVY_PASSWORD=*your API key for IBM TaaS Artifactor*, created earlier in Artifactory
3. Clone Git repo ca-branch-configurations as ~/branch-configurations  e.g. in your home directory run git clone **https://github.com/aipoweredmarketer/ca-branch-configurations.git**
4. Clone Git repo ca-build-common as ~/build-common  e.g in your home directory run git clone **https://github.com/aipoweredmarketer/ca-build-common.git**
5. In your environment, set environment variable **BUILD_COMMON_RELEASE=master.**
6. Clone Git repo for any Campaign project which uses Ant (build.xml file) and change to the directory for the project.
7. You will also need to set some environment variables: 
   * **CM_HOME=path to folder which contains /branch-configurations and /build-common folders.** e.g (CM_HOME=C:\DevEnvironment\borisov\borisov_engage)

8. You should now be able to run **'ant clean resolve make'** to build the Campaign project.

*Notes:* *you alse need to have java environment set, and be able clone reposiroties via ssh*
