pipeline {
    stage('Run Playbook') {
      environment {
        ANSIBLE_MY_PARAM="new_param"
      }
      steps {
        script {
            config = readFile "config.yaml"
            newconfig = a.replaceAll("{v1}","${ANSIBLE_MY_PARAM}")
            writeFile file: "config.yaml", text: "${newconfig}"
        }
    }
}

