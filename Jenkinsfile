script {
config = readFile "config.yaml"
newconfig = config.replaceAll("v1","new")
writeFile file: "config.yaml", text: "${newconfig}"
config2 = readFile "config.yaml"
echo config2
}
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
