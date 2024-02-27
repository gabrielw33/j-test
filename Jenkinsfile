def configFile = "conf/param.yaml"

beforeAgent {
    // Read the YAML file
    def config = readFile configFile
    
    // Modify the content
    def newConfig = config.replaceAll("dd", "fase")
    
    // Write the modified content back to the file
    writeFile file: configFile, text: newConfig
    
    // Echo the modified content
    echo "Modified configuration:"
    echo newConfig
}

pipeline {
    agent any
    stages {
        stage("conf") {
            steps {
                script {
                    echo aa
                }
            }
        }
    }
}
