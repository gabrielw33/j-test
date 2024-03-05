pipeline {
    agent any


    stages {
        stage('Replace Parameters') {
            steps {
                script {
                    def branch_name = "develpo" 
                    def test_env_bq = "mlwbrisk"
                    yamlContent = readYaml: (file: 'conf/param.yaml') 

                    if (branch_name == "master"){
                        yamlContent.dastination.table_id = yamlContent.dastination.table_id.replace("{branch_name}", "")
                        yamlContent.dastination.project_id = test_env_bq       
                    }else{
                        yamlContent.dastination.table_id = yamlContent.dastination.table_id.replace("{branch_name}", "-${branch_name}")
                        yamlContent.dastination.project_id = test_env_bq
                    }

                    echo "${yamlContent}"
                }
            }
        }
    }
}

