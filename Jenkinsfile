pipeline {
    agent any


    stages {
        stage('Replace Parameters') {
            steps {                                    
                script {
                    def allowNotParams = False
                    
                    def branch_name = "develop" 
                    def test_env_bq = "mlwbrisk"
                    def prod_env_bq = "pipelines"
                    
                    def paramList = [prod_env_bq, test_env_bq, branch_name]
                    def paramFileContent = readFile(file: 'config.yaml')
     
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
                    

                    echo "${paramFileContent}"
                }
            }
        }
    }
}

