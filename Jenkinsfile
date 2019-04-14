node {
   def mvnHome
   stage('Preparation') { // for display purposes
      // Get some code from a GitHub repository
      checkout scm
   }
   stage('Build') {
      // Run the maven build
      mvnHome = tool name: '3.6.0', type: 'maven'
      mvn -Dmaven.test.failure.ignore clean package
      //sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
   }
   stage('Results') {
    sh 'scp tlt/target/tlt.war some-remote-host:/LOCATION/TOMCAT/webapps/'
  }
}