pipeline {
    agent any
    
//    agent { 
//        docker { 
//            image "maven:3.8.2-amazoncorretto-8" 
//        } 
//    }
      
//    tools {
//        maven "3.6.3" 
//    }

//    agent {
//        dockerfile true   
//    }
    
    stages {

        stage("Build") {
            steps {
                sh "docker --version"
                sh "docker ps -a"
                sh "docker images"
                sh "mvn -version"
//                sh "mvn clean install"
            }
        }

        stage("Run") {
            steps {
                echo 'step run message'
                sh 'mvn compile exec:java -Dexec.mainClass="com.example.folder.test"'
            }
        }

    }

    post {
        always {
            cleanWs()
            sh "docker system prune -a"
            echo 'post always message'
        }
    }


}
