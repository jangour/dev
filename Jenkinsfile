pipeline {
    agent any

//    environment {
  //      docker_cred = credentials('docker_cred')
  //  }

    stages {

    
        
//        stage('Unit Tests') {
 //           steps {
                
   //             sh "mvn test"
   //         }
   //     }
        
        

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

        stage('Deploy to Nexus') {
            steps {
                dir('back'){
                    //def nexusCredentials = credentials('2')
                sh 'mvn deploy -DskipTests'
                    }        
                }
            }        


//        stage('SonarQube Analysis') {
//            steps {
//                dir('back') {
//                       withSonarQubeEnv('sonarserver') {
//                                      sh 'mvn sonar:sonar -Dsonar.java.binaries=target/classes'
//            }
//                }
               
//       }
//       }













    }
}
