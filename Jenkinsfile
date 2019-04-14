node {
   def mvnHome
   stage('Preparation') { // for display purposes
      // Get some code from a GitHub repository
      git 'https://github.com/giora83/DevopsPractice.git'
   }
   stage('Build') {
      // Run the maven build
      mvnHome = tool name: '3.6.0', type: 'maven'
      sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
   }
   stage('Results') {
    sh 'scp tlt/target/tlt.war some-remote-host:/LOCATION/TOMCAT/webapps/'
  }
}