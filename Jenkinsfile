pipeline {
    agent any
    stages {
        stage('conf') {
          steps {
                config = readFile "config.yaml"
                newconfig = a.replaceAll("{v1}","new")
                writeFile file: "config.yaml", text: "${newconfig}"
          }
       }
   }
}
