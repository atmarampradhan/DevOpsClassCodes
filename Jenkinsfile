pipeline {
  agent any
  stages {
    stage('checkout scm') {
        steps {
            script{
                git credentialsId: 'a618bfad7e2cae4c029afaaff506a8c32025c465', url: 'ssh://git@github.com:atmarampradhan/DevOpsClassCodes.git'
                sh 'git branch -r | awk \'{print $1}\' ORS=\'\\n\' >>branch.txt'
            }

        }
    }
     stage('get build Params User Input') {
        steps{
            script{

                liste = readFile 'branch.txt'
                echo "please click on the link here to chose the branch to build"
                env.BRANCH_SCOPE = input message: 'Please choose the branch to build ', ok: 'Validate!',
                        parameters: [choice(name: 'BRANCH_NAME', choices: "${liste}", description: 'Branch to build?')]


            }
        }
    } 

  }
}
