

pipeline{

    agent any

    stages {

        stage('Checkout code') {
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'SubmoduleOption', disableSubmodules: false, parentCredentials: false, recursiveSubmodules: true, reference: 'https://github.com/b3log/solo-skins', trackingSubmodules: false]], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'd764d34d-ff72-4438-ac5c-886528552ab0', url: 'https://github.com/jun-wang-decathlon/solo.git']]])            }
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
