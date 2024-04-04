pipeline {
  agent any
  tools { 
      maven 'DHT_MVN' 
      jdk 'DHT_SENSE' 
  }
  stages {
    stage('Checkout') {
      steps {
        git(url: 'https://github.com/nigelqiu/maven-samples-A6-se.git', branch: 'master')
      }
    }

    stage('Reset') {
      steps {
        bat 'git bisect reset'
      }
    }

    stage('Bisect') {
      steps {
        bat 'git bisect start 198644632661c67b6c32f59e9047c11a70685e15 98ac319c0cff47b4d39a1a7b61b4e195cfa231e5'
      }
    }

    stage('Run') {
      steps {
        bat 'git bisect run mvn clean test'
      }
    }
  }
}
