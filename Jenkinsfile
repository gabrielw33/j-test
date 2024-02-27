@Library('test-shared-lib')_
node{script{
    if (atb == true){
        config = readFile "config.yaml"
        newconfig = config.replaceAll("v1","new")
        writeFile file: "config.yaml", text: "${newconfig}"
    } 
    else
    {
        config = readFile "config.yaml"
        newconfig = config.replaceAll("v1","none")
        writeFile file: "config.yaml", text: "${newconfig}"
    }

    config2 = readFile "config.yaml"
    echo config2
}}

demo()
