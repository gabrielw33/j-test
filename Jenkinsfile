pipeline {
    agent any

    stages {
        stage('Read YAML') {
            steps {
                script {
                    def bs = "jej"
                    def yamlContent = readYaml(file: 'conf/param.yaml')
                    def filledYaml = replaceParams(yamlContent)
                    echo "${filledYaml}"
                }
            }
        }
    }
}

def replaceParams(yamlContent) {
    yamlContent.collectEntries { key, value ->
        [(key): replaceParamsRecursively(value)]
    }
}

def replaceParamsRecursively(value) {
    if (value instanceof Map) {
        return replaceParams(value)
    } else if (value instanceof List) {
        return value.collect { replaceParamsRecursively(it) }
    } else if (value instanceof String) {
        return env.expand(value)
    } else {
        return value
    }
}
