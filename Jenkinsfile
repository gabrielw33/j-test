pipeline {
    agent any

    stages {
        stage('Read YAML') {
            steps {
                script {
                    def bs = "jej"
                    def yamlContent = readYaml(file: 'conf/param.yaml')
                    def filledYaml = evaluate(yamlContent)
                    echo "${filledYaml}"
                }
            }
        }
    }
}

