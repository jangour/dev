pipeline {
    agent any

        environment {
        withCredentials([usernamePassword(credentialsId: 'dockerhub', usernameVariable: 'dockerhubN', 
                                          passwordVariable: 'dockerhubP')]) {
        sh "docker login -u $dockerhubN -p $dockerhubP"
    // Now you can push Docker images to Docker Hub
}

    }
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




    stages {
        stage('Build and Push Docker Images') {
            steps {
                script {
                    // Build and tag the Spring Boot backend image
                    sh "docker build -t your-dockerhub-username/back:latest -f Dockerfile ."
                    sh "docker push your-dockerhub-username/back:latest"
                    
                    // Build and tag the Angular frontend image
                    sh "docker build -t dockerhubN/front:latest -f Dockerfile ."
                    sh "docker push dockerhubN/front:latest"
                }
            }
        }
    }







    }
}
