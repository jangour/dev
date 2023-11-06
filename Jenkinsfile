pipeline {
    agent any

//    environment {
  //      docker_cred = credentials('docker_cred')
  //  }

    stages {

        stage('Build Backend') {
            steps {
                dir('DevOps_Project'){
                sh 'mvn clean package'
            }
        }
        }


        stage('Build Frontend') {
            steps {
                script {
                    dir('DevOps_Project_Front') {
                        
                        sh 'npm install'
                        sh 'ng build --prod'
                    }
                }
            }
        }

        stage('Code Analysis') {
            steps {
                script {
                    dir('DevOps_Project'){
                    def scannerHome = tool name: 'SonarQubeScanner', type: 'Tool'
                    withSonarQubeEnv('SonarQube') {
                        sh "${scannerHome}/bin/sonar-scanner"
                        }
                    }
                }
            }
        }


        stage('Unit Tests') {
            steps {
                
                sh "mvn test"
            }
        }


        stage('Deploy to Nexus') {
            steps {
                dir('DevOps_Project'){
                sh 'mvn deploy -DskipTests'
                    }        
                }
            }







    }
}
