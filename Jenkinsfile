 pipeline{
  agent any
  stages{
    stage('Clone repository'){
      steps{
        checkout([$class: 'GitSCM',
                branches: [[name: '*/main']],
                userRemoteConfigs: [[url: 'https://github.com/hiimsha7979/PES1UG22CS810_Jenkins.git']]
      ])
      }
    }
    stage('Build'){
      steps{
        build 'PES1UG22CS810-1'
        sh 'g++ main2.cpp -o output'
      }
    }
    stage('Test'){
      steps{
        sh './output'
      }
    }
    stage('Deploy'){
      steps{
        echo 'deploy'
      }
    }
  }
  post {
    failure {
      error 'Pipeline failed'
    }
  }

  
} 
