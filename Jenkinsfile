pipeline {
    agent any

    stages {

        stage("Build") {
            steps {
                sh "mvn -version"
                sh "mvn clean install"
            }
        }

        stage("Run") {
            steps {
                sh 'mvn compile exec:java -Dexec.mainClass="com.example.folder.test"'
            }
        }

    }

    post {
        always {
            cleanWs()
        }
    }


}
