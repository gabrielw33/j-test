node{
    script{

    def configFile = "conf/param.yaml"
    
    // Read the YAML file
    def config = readFile configFile
    
    // Modify the content
    def newConfig = config.replaceAll("dd", "lul")
    
    // Write the modified content back to the file
    writeFile file: configFile, text: newConfig
    
    // Echo the modified content
    echo "Modified configuration:"
    echo newConfig
    }
    
}


pipeline {
    agent any
    stages {
        stage("conf") {
            steps {
                script {
                    echo "Using modified configuration in the pipeline:"
                    
                    // Now you can use the modifiedConfig as needed
                    // do_something(modifiedConfig)
                }
            }
        }
    }
}
