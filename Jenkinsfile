pipeline {
//    agent any
    
//    agent { 
//        docker { 
//            image "maven:3.8.2-amazoncorretto-8" 
//        } 
//    }
      
//    tools {
//        maven "3.6.3" 
//    }

    agent {
        dockerfile true   
    }
    
    
    stages {

        stage("Build") {
            steps {
//                sh "node --version"
//                sh "svn --version"
//                sh "docker --version"
//                sh "docker ps -a"
//                sh "docker images"
                sh "mvn -version"
//               sh "mvn clean install"
            }
        }

        stage("Run") {
            steps {
                echo 'step run message'
                sh 'mvn compile exec:java -Dexec.mainClass="com.example.folder.test"'
            }
        }

        stage ("Test") {
            steps {
                echo 'step test message'   
                echo 'vim'
            }
            
        }
        
//        stage('Sanity check') {
//            steps {
//                input "Does the staging environment look ok?"
//            }
//        }
  
        stage("Deploy") {
            steps {
                echo 'Deploying ... message'     
            }
        }
        
    }
    
    
//////////////////////////////////////////////////////////////    
   
    
    post {      
        always {
            cleanWs()
//          input "docker system prune -a"
            echo 'post always message'
        }
        success {
            echo 'post success message'   
        }
        unstable {
            echo 'post unstable message'   
        }        
        failure {
            echo 'post fail message'   
        }        
        changed {
            echo 'post -things were changed message'   
        }
         
        
    }

 ////////////////////////////////////////////////////////////////

    
    
}
