pipeline{
    agent { label 'AGENT-1' } //jenkins node name
    environment{
        PROJECT = 'expense'     //We can use these as global variables
        COMPONENT = 'backend' 
        appVersion = ''
    }
    options{
        disableConcurrentBuilds() 
        timeout(time: 30, unit: 'MINUTES')
    }
     /* parameters{
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    } */
    stages{
        stage('Read Version'){
            steps{
                script{
                    def packageJson = readJson file: 'package.json'
                    env.appVersion = packageJson.version
                    echo "Version is: $appVersion"
                }
            }
        }
    } 
    post{
        always{
            echo 'I will always say Hello again!'
            deleteDir() //it will deletes the directory
        }
        failure{
            echo 'I will run when pipeline is failed'
        }
        success{
            echo 'I will run when pipeline is success'
        }
    }
}