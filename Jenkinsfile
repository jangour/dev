pipeline {
    agent any
        environment {
        docker_cred = credentials('dockerhub')
    }
    stages {

/*        stage('Build Backend') {
            steps {
                dir('back'){
                sh 'mvn clean package'
            }
        }
        } 
        stage('Deploy to Nexus') {
            steps {
                dir('back'){
                    //def nexusCredentials = credentials('2')
                sh 'mvn deploy -DskipTests'
                    }        
                }
            }  
        
        stage('SonarQube Analysis') {
            steps {
                          dir('back') {
                    // Use Maven to build the application
                      sh 'mvn sonar:sonar -Dsonar.login=squ_cdf1e27b6ae375e378a47e6ef724dcfde408d870'
                }
             
            }
        }
*/        
stage('Build Angular Frontend') {
        steps {
            script {
                // Set the PATH to include the directory where npm and node are installed
                def nodeBin = tool 'NodeJS' // Replace with the actual tool name
                def nodePath = "${nodeBin}/bin"
                env.PATH = "${nodePath}:${env.PATH}"
        
                // Navigate to the Angular project directory
                dir('front') {
                    // Install project dependencies
                    sh 'npm install'
        
                    // Build the Angular application
                    sh 'npm run build'
                }
            }
        }
    }


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




   /*      stage('Build and Push Backend Image') {
             steps {
                  script {
                    dir('back') {
                            sh "docker login -u achref5 -p achrefjang5"
                            // Build your Docker image
                            sh "docker build -t achref/devopsbackendproject:1.0 ."
                            // Push the image
                            sh "docker push achref/devopsbackendproject:1.0"
                }
            }
        }
         }*/




    

    




/*        stage('Unit Tests') {
            steps {
                
                sh "mvn test"
            }
        }
   */     


    }
}
