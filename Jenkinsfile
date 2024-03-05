pipeline {
    agent any

    environment {
        BN = 'wartość_zmiennej'
    }

    stages {
        stage('Replace Parameters') {
            steps {
                script {
                    def yamlContent =  Eval.me("[a:\${BN}, b:\${BN}, c:\${BN}]")
                    def filledYaml = replaceParameters(yamlContent)
                    echo "${filledYaml}"
                }
            }
        }
    }
}

