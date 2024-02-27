node{script{

    config = readFile "conf/param.yaml"
    newconfig = config.replaceAll("dd","fase")
    writeFile file: "conf/param.yaml", text: "${newconfig}"


    config2 = readFile "conf/param.yaml"
    echo config2
}}
