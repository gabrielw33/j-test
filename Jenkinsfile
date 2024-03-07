pipeline {
    agent any


    stages {
        stage('Replace Parameters') {
            steps {                                    
                script {
                    def branch_name = "develop" 
                    def test_env_bq = "mlwbrisk"
                    def prod_env_bq = "pipelines"
                    
                    def paramFileContent = readFile(file: 'conf/param.yaml')
                    echo "${test_env_bq}"

                    if (branch_name == "master"){
                        paramFileContent = paramFileContent.replace("{branch_name}", "")
                        paramFileContent = paramFileContent.replace("{pipelines}", "${prod_env_bq}") 
                    }else{
                        paramFileContent = paramFileContent.replace("{branch_name}", "-${branch_name}")
                        paramFileContent = paramFileContent.replace("{pipelines}", "${test_env_bq}")
                    }

                    echo "${paramFileContent}"
                }
            }
        }
    }
}

