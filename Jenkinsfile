node {
   def mvnHome
   stage('Preparation') { // for display purposes
      // Get some code from a GitHub repository
      checkout scm
   }
   stage('Build') {
      // Run the maven build
      mvnHome = tool name: '3.6.0', type: 'maven'
      sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
   }
   stage('Deploy to tomcat') {
    mvn tomcat7:deploy
  }
}