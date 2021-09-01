pipeline {
    agent any

    stages {

        stage("Build") {
            steps {
                sh "mv -version"
                sh "mvn clean install"
            }
        }

    }

    post {
        always {
            cleanWs()
        }
    }


}