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
        bat 'py -m py_compile app.py'
      }
    }

    stage('Test'){
      steps{
        echo 'Executing automated tests'
        bat 'py -m unittest app'
      }
    }
    stage('Run application'){
      steps{
        bat 'py app.py'
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
