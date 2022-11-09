pipeline {
  agent any
  environment {
    NEW_VERSION = '1.3'
  }
  stages {

    stage("build") {
      steps {
        echo "bulding the app..."
        echo "building version ${NEW_VERSION}"
      }
    }

    stage("test") {
      when {
        expression {
          BRANCH_NAME == 'dev' || BRANCH_NAME == 'master'
        }
      }
      steps {
        echo "testing the app..."
      }
    }

    stage("deploy") {
      steps {
        echo "deploying the app..."
      }
    }
  }
  post {
    always {
      echo "always section"
    }
    success {
      echo "sucess section"
    }
    failure {
      echo "failure section"
    }
  }
}