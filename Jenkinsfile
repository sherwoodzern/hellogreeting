pipeline {
    agent {
        node {
            label "Jenkinsslave"
        }
    }
    
    tools {
        maven 'M3'
    }
    environment {
        DOCKER_REGISTRY='iad.ocir.io/oraclegilsonmel/greeting'
    }
    stages {
        stage('build') {
            steps {
                withMaven(
                    maven: 'M3',
                    mavenLocalRepo: '.repository',
                    mavenSettingsConfig: 'global-settings-xml'
                ) {
                    sh 'mvn install'
                    sh 'mvn package'
                }
            }
        }
    }
}