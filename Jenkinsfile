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
                sh "docker build -t hello_there ."
//                sh "mvn -version"
//                sh "mvn clean install"
            }
        }

        stage("Run") {
            steps {
                sh "docker run --rm hello_there
/*                sh 'mvn compile exec:java -Dexec.mainClass="com.example.folder.test"'
*/            }
        }

    }

    post {
        always {
            // cleanWs()
            echo 'post always message'
        }
    }


}
