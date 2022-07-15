pipeline {
    agent any
    
    environment{
        PATH = "/opt/maven/bin:$PATH"
    }

    stages {
        stage('Hello') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/heysai/hello-world']]])
            }
        }
        stage('build') {
            steps {
                sh "mvn clean install"
            }
        }
    }
}
