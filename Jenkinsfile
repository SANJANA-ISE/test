pipeline{
  agent any
  stages{
    stage('Checkout'){
      steps{
        checkout scm
      }
    }
    stage('Build'){
      steps{
        echo 'Checking python application'
        bat 'Python -m py_compile app.py'
      }
    }

    stage('Test'){
      steps{
        echo 'Executing automated tests'
        bat 'Python -m unittest app'
      }
    }
    stage('Run application'){
      steps{
        bat 'python app.py'
      }
    }
  }
  post{
    success{
      echo 'CI pipeline completed sucessfully'
    }
    failure{
      echo 'CI pipeline Failed'
    }
  }
}
