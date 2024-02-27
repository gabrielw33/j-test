@Library('test-shared-lib')_
node{script{


    echo "fs"
    config = readFile "conf/param.yaml"
    newconfig = config.replaceAll("dd","fase")
    writeFile file: "config.yaml", text: "${newconfig}"


    config2 = readFile "conf/param.yaml"
    echo config2
}}
