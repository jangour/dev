pipeline {
    agent any

//    environment {
  //      docker_cred = credentials('docker_cred')
  //  }

    stages {

        stage('Build Backend') {
            steps {
                dir('back'){
                sh 'mvn clean package'
            }
        }
        }


    //    stage('Build Frontend') {
     //       steps {
        //        script {
          //          dir('front') {
                        
           //             sh 'npm install'
           //             sh 'ng build --prod'
          //          }
          //      }
        //    }
     //   }

        stage('Code Analysis') {
            steps {
                script {
                    dir('back'){
                    def scannerHome = tool name: 'SonarQubeScanner', type: 'Tool'
                    withSonarQubeEnv('SonarQube') {
                        sh "${scannerHome}/bin/sonar-scanner"
                        }
                    }
                }
            }
        }


//        stage('Unit Tests') {
 //           steps {
                
   //             sh "mvn test"
   //         }
   //     }


        stage('Deploy to Nexus') {
            steps {
                dir('back'){
                sh 'mvn deploy -DskipTests'
                    }        
                }
            }







    }
}
