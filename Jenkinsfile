@Library('test-shared-lib')_
node{script{


    echo "fs"
    config = readFile "config.yaml"
    newconfig = config.replaceAll("v3","fase")
    writeFile file: "config.yaml", text: "${newconfig}"


    config2 = readFile "config.yaml"
    echo config2
}}

demo()
