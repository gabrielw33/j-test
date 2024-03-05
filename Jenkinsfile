pipeline {
    agent any

    environment {
        BN = 'wartość_zmiennej'
    }

    stages {
        stage('Replace Parameters') {
            steps {
                script {
                    def yamlContent = "[a:\${BN}, b:\${BN}, c:\${BN}]"
                    def filledYaml = replaceParameters(yamlContent)
                    echo "${filledYaml}"
                }
            }
        }
    }
}

def replaceParameters(template) {
    def engine = new groovy.text.SimpleTemplateEngine()
    def binding = [BN: env.BN]
    def interpolatedTemplate = engine.createTemplate(template).make(binding)
    return interpolatedTemplate.toString()
}
