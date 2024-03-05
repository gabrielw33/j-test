pipeline {
    agent any


    stages {
        stage('Replace Parameters') {
            steps {
                script {
                    def branch_name = "develpo" 
                    def test_env_bq = "mlwbrisk"
                    def prod_env_bq = "pipelines"
                    yamlContent = readYaml(file: 'conf/param.yaml')
                    echo "${test_env_bq}"

                    if (branch_name == "master"){
                        yamlContent.dastination.table_id = yamlContent.dastination.table_id.replace("{branch_name}", "")
                        yamlContent.dastination.project_id = yamlContent.dastination.project_id.replace("{pipelines}", "${prod_env_bq}") 
                    }else{
                        yamlContent.dastination.table_id = yamlContent.dastination.table_id.replace("{branch_name}", "-${branch_name}")
                        yamlContent.dastination.project_id = yamlContent.dastination.project_id.replace("{pipelines}", "${test_env_bq}") 
                    }

                    echo "${yamlContent}"
                }
            }
        }
    }
}

