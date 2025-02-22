pipeline {
    agent {
        node {
            label 'AGENT-1'
            }
        }
    environment {
        packageVersion = ''
        nexusUrl = '187.21.8.89:8081' //private_ip of nexus instance, here we must put port number also.
     }
    options {
        timeout(time: 1, unit: 'HOURS')
        disableConcurrentBuilds()
    }
    parameters {
        booleanParam(name: 'Deploy', defaultValue: false, description: 'Toggle this value')
    }
    // build
    stages {
        stage('Get the version') {
            steps {
                script {
                    def packageJson = readJSON file: 'package.json' 
                    packageVersion = packageJson.version
                    echo "application version: $packageVersion"
                    }
                }
            }
        }
    // post build
    post { 
        always { 
            echo 'I will always say Hello again!'
            deleteDir()
        }
        failure { 
            echo 'this runs when pipeline is failed, used generally to send some alerts'
        }
        success{
            echo 'I will say Hello when pipeline is success'
        }
    }
}