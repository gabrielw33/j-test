@Library('test-shared-lib')_
node{script{
    echo env.GIT_BRANCH
    config = readFile "config.yaml"
    newconfig = config.replaceAll("v1","new")
    writeFile file: "config.yaml", text: "${newconfig}"
    config2 = readFile "config.yaml"
    echo config2
}}

demo()
