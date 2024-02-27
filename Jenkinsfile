node{
    script{
    def bn = "dup" 
    def configFile = "conf/param.yaml"
    
    // Read the YAML file
    def config = readYaml file: configFile
    
    // Modify the content
    config.a = config.a + "-${bn}" 
    echo config.a
    // Write the modified content back to the file
    writeYaml file: configFile, data: config, overwrite: true
    
    // Echo the modified content
    echo "Modified configuration:"
    }
    
}

node{
    script{
               echo "Using modified configuration in the pipeline:"
                    def configFile = "conf/param.yaml"
    
                    // Read the YAML file
                    def config = readYaml file: configFile
                    echo config.a
    
    }
    
}


