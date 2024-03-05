pipeline {
    agent any

    environment {
        BN = 'wartość_zmiennej'
    }

    stages {
        stage('Replace Parameters') {
            steps {
                script {
                    def yamlContent =  Eval.me("2+2")
                    echo "${yamlContent}"
                }
            }
        }
    }
}

