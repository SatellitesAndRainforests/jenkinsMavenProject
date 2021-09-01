pipeline {
//    agent any
//    agent { docker { image"maven:3.8.2-amazoncorretto-8" } } 
    environment {
        JAVA_TOOL_OPTIONS = "-Duser.home=/home/jenkins"   
    }
    agent {
        dockerfile {
            label "docker" /////////////////////////////// add label docker to master node <------------
            args "-v /tmp/maven:/home/jenkins/.m2 -e MAVEN_CONFIG=/home/jenkins/.m2"
        }
    }
    
//    tools {
//        maven "3.6.3" 
//    }

    stages {

        stage("Build") {
            steps {
                sh "ssh -V"
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
