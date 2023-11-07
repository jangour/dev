pipeline {
    agent any
    stages {

    
        
/*        stage('Unit Tests') {
            steps {
                
                sh "mvn test"
            }
        }
   */     
        

 /*       stage('Build Backend') {
            steps {
                dir('back'){
                sh 'mvn clean package'
            }
        }
        }
*/
    /*    stage('Build Frontend') {
            steps {
                script {
                    dir('front') {
                        
                        sh 'npm install'
                        sh 'ng build --prod'
                    }
                }
            }
        }*/

  /*      stage('Deploy to Nexus') {
            steps {
                dir('back'){
                    //def nexusCredentials = credentials('2')
                sh 'mvn deploy -DskipTests'
                    }        
                }
            }        
*/

 /*       stage('SonarQube Analysis') {
             steps {
                dir('back') {
                       withSonarQubeEnv('sonarserver') {
                                       sh 'mvn clean package sonar:sonar'
            }
                }
               
       }
       }
*/




    
        stage('Build and Push Docker Images') {
            steps {
                script {
                    
                    // Build and tag the Spring Boot backend image
                    sh "docker build -t dockerhubN/back:latest -f /back/Dockerfile ."
                    sh "docker push dockerhubN/back:latest"
                    
                    // Build and tag the Angular frontend image
                    sh "docker build -t dockerhubN/front:latest -f /front/Dockerfile ."
                    sh "docker push dockerhubN/front:latest"
                            withCredentials([usernamePassword(credentialsId: 'dockerhub', usernameVariable: 'dockerhubN', 
                                          passwordVariable: 'dockerhubP')]) {
                            sh "docker login -u $dockerhubN -p $dockerhubP"
                            // Now you can push Docker images to Docker Hub
                        }
                }
            }
        }
    







    }
}
