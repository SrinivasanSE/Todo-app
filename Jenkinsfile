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
                echo "${hello}"
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
    }
}
def myFunc(String flag) {
        echo "${flag}"
}
