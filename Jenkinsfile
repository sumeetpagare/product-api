pipeline {

  agent any
  
   environment {
    Maven_Home="C:\\maven\\apache-maven-3.8.6\\bin"
    M2SETTINGS = "C:\\Users\\sumit\\.m2\\settings.xml"
  }

  stages {
    stage('Build') {
      steps {
            bat 'mvn -B -U -e -V clean -DskipTests package'
      }
    }

    stage('Test') {
      steps {
          echo "***** MUnit Test cases execution *****"
      }
    }

     stage('Deploy Development') {
      steps {
            bat 'mvn -U -V -e -B -DskipTests -Pdev deploy -DmuleDeploy 
      }
    }
  }
}