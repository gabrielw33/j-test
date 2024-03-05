pipeline {
    agent any

    environment {
        BN = 'wartość_zmiennej'
    }

    stages {
        stage('Replace Parameters') {
            steps {
                script {
                    def yamlContent = "[a:\${env.BN}, b:\${env.BN}, c:\${env.BN}]"
                    def filledYaml = evaluateTemplate(yamlContent)
                    echo "${filledYaml}"
                }
            }
        }
    }
}

@NonCPS
def evaluateTemplate(template) {
    // Parse template with Groovy's SimpleTemplateEngine
    def engine = new groovy.text.SimpleTemplateEngine()
    def binding = new groovy.util.GroovyScriptEngine(this.class.classLoader).with {
        createBindings([env: env])
    }
    def compiledTemplate = engine.createTemplate(template).make(binding)
    // Return evaluated template
    return compiledTemplate.toString()
}
