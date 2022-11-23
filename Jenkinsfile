pipeline {
    agent any
    parameters {
        string(defaultValue:"Yes", name:"isGood", description:"testing..")
    }
    environment {
        def hello = "Hello"
    }
    stages {
        stage('first') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: 'refs/heads/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/SrinivasanSE/Todo-app']]])
                 }
        }
        stage('second') {
            steps {
               script {
                if (params.isGood == "Yes") {
                    echo "Hello ${params.isGood}"
                }
                else {
                    echo "waste"
                }
            }
            }
        }
         stage('third') {
            steps {
                myFunc("seenu")
            }
        }
         stage('executing') {
            steps {
                bat "python test.py"
            }
        }
    }
}
def myFunc(String flag) {
        echo "${flag}"
}
