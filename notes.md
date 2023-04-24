# Maven

1. Login to the agent as root
2. Download maven from `https://maven.apache.org/download.cgi`
    e.g. `curl -O https://dlcdn.apache.org/maven/maven-3/3.9.1/binaries/apache-maven-3.9.1-bin.zip`
3. Unzip `unzip apache-maven-3.9.1-bin.zip`
4. Move the folder to `/opt`
5. In Jenkins, navigate to "manage jenkins" then "global tool configuration"
6. Scroll down to "Maven" and under "Name" enter "maven-3.9.1"
7. Under "MAVEN_HOME" enter the path to the maven installation which in this case is `/opt/apache-maven-3.9.1`
8. Make sure "install automatically" is not checked and click save
9. In your pipeline script, make sure you have included maven in the "tool" section
` tools {
        maven 'MAVEN' 
    }'
10. Run the build

You may also need to add the mavin bin to path if you are getting an error regarding not being able to find the command mvn

For system-wide PATH
`nano /etc/login.defs`
Add the line `export PATH="$PATH:/opt/apache-maven-3.9.1/bin"`

For user session PATH
`nano ~/.bashrc`
Add the line `export PATH="$PATH:/opt/apache-maven-3.9.1/bin"`
