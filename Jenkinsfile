dnode{
    script{

    def configFile = "conf/param.yaml"
    
    // Read the YAML file
    def config = readYaml file: configFile
    
    // Modify the content
    config.c
    echo config
    // Write the modified content back to the file
    writeYaml file: configFile, data: config, overwrite: true
    
    // Echo the modified content
    echo "Modified configuration:"
    echo config
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
