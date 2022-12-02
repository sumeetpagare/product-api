pipeline {

  agent any
  
   environment {
   
    
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
            bat 'mvn -U -V -e -B -DskipTests -Pdev deploy -DmuleDeploy'
      }
    }
  }
}