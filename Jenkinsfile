@Library('jenkins-shared-library')_

def configMap = [
    project: "expense",
    component: "backend"
]

if ( ! env.BRANCH_NAME.equalsIgnoreCase('main')){
    nodeJSEKSPipeline(configMap)
}
else{
    echo "Please follow production process"
}