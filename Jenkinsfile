def PrintStageName() {
  echo "-----------------${env.STAGE_NAME}-----------------"
}

pipeline {

   agent { label 'linux-agents' }

   environment {
     USER_NAME = "joesmith"
     USER_ID = 115
   }   

   stages {

      stage("STAGE-ENVIRONMENT-VARIABLES"){
        steps{
          PrintStageName()
          echo "BUILD_NUMBER = ${env.BUILD_NUMBER}"
        }
      }

        stage('STAGE-GET-REPO')  {
               
            steps {
              PrintStageName()
                script {
                     try{
                           // Get some code from a GitHub repository
                           git url: 'https://github.com/fedora800/projCert.git', branch: 'main' 
                      
                     }
                     catch (err){
                           echo err
                     }
                }
             }
        }

        // stage-monitor
        stage("STAGE-MONITOR") {
            steps { 
              PrintStageName()
              echo "Monitor"  
            }
        }

    } // end-stages


}

