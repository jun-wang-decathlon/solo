

pipeline{

    agent any

    stages {

        stage('Checkout code') {
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'SubmoduleOption', disableSubmodules: false, parentCredentials: false, recursiveSubmodules: true, reference: '', trackingSubmodules: false]], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '3eecf9dd-5d94-405b-811c-f3acf28b94f7', url: 'https://github.com/jun-wang-decathlon/solo.git']]])
        }
        }

        stage('build') {
            steps {
               sh "mvn clean package -Dmaven.test.skip=true"
            }
        }


        stage('Build docker image') {
            steps {
               sh "echo build docker image ok."
            }
        }
    }
}
