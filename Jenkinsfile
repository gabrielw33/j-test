pipeline {
    agent any


    stages {
        stage('Replace Parameters') {
            steps {                                    
                script {
                    def allowNotParams = false
                    
                    final branch_name = "develop" 
                    final test_env_bq = "mlwbrisk"
                    final prod_env_bq = "pipelines"

                    final kedroConfigFilePath = "conf/param.yaml"
                    def paramList = [prod_env_bq, test_env_bq, branch_name]
                    def paramFileContent = readFile(file: kedroConfigFilePath)
     
                    //paramFileContent.indexOf(substring)

                    def found = paramList.any { searchString -> paramFileContent.contains(searchString) }
                    echo "${found}"
                    if (!found && !allowNotParams){
                        error("Error encountered: Something went wrong!")
                    }
                       
                    if (branch_name == "master"){
                        paramFileContent = paramFileContent.replace("{branch_name}", "")
                        paramFileContent = paramFileContent.replace("{pipelines}", "${prod_env_bq}") 
                    }else{
                        paramFileContent = paramFileContent.replace("{branch_name}", "-${branch_name}")
                        paramFileContent = paramFileContent.replace("{pipelines}", "${test_env_bq}")
                    }
                    writeFile file: kedroConfigFilePath, text: paramFileContent

                    echo "${paramFileContent}"
                }
            }
        }
    }
}

