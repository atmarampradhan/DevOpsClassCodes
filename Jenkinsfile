pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn build'
      }
    }
   stages{

    stage('checkout scm') {
        steps {
            script{
                git credentialsId: 'a618bfad7e2cae4c029afaaff506a8c32025c465', url: 'ssh://jenkins@git.company.com:/usr/company/repositories/repo.git'
                sh 'git branch -r | awk \'{print $1}\' ORS=\'\\n\' >>branch.txt'
            }

        }
    }
     
     
  }
}
