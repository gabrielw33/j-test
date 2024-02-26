pipeline {
    agent any
    stages {
        stage("conf") {
          steps {
              script {
                config = readFile "config.yaml"
                newconfig = config.replaceAll("v1","new")
                writeFile file: "config.yaml", text: "${newconfig}"
                config2 = readFile "config.yaml"
                echo config2
              }
          }
       }
   }
}
