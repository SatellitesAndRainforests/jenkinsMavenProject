pipeline {
//    agent any
    agent {
        docker {
            image "maven:3.6.3-amazoncorretto-8"  
            label "master"
        }
    }
    
//    tools {
//        maven "3.6.3" 
//    }

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
