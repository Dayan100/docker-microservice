node {
  stage('SCM Checkout') {
    git 'https://github.com/harishanumandla817/docker-microservice.git'
  }
    stage('Compile-Package') {
      def mvnHome = tool name: 'Apache Maven 3.3.9', type: 'maven'
      //"${mvnHome}/bin/mvn package"
      "${mvnHome}/bin/mvn package"
    }
  stage ('Build') {
 
    git url: 'https://github.com/harishanumandla817/docker-microservice.git'
 
    withMaven(
        // Maven installation declared in the Jenkins "Global Tool Configuration"
        maven: 'M3',
        // Maven settings.xml file defined with the Jenkins Config File Provider Plugin
        // Maven settings and global settings can also be defined in Jenkins Global Tools Configuration
        mavenSettingsConfig: 'my-maven-settings',
        mavenLocalRepo: '.repository') {
 
      // Run the maven build
      sh "mvn clean install"
 
    } // withMaven will discover the generated Maven artifacts, JUnit Surefire & FailSafe & FindBugs reports...
  }
}
