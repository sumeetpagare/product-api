pipeline {

  agent any
  
   environment {
   
    M2SETTINGS = "C:\\Users\\sumit\\.m2\\settings.xml"
  }

  stages {
    stage('Build') {
      steps {
            bat 'mvn -B -U -e -V clean -gs %M2SETTINGS% -DskipTests package'
      }
    }

    stage('Test') {
      steps {
          echo "***** MUnit Test cases execution *****"
      }
    }

     stage('Deploy Development') {
      steps {
            bat 'mvn -U -V -e -B -gs %M2SETTINGS% -DskipTests -Pdev deploy -DmuleDeploy'
      }
    }
  }
}