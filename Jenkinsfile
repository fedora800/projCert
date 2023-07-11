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
          echo "[1] - BUILD_NUMBER = ${env.BUILD_NUMBER}"
          sh 'echo [2] - BUILD_NUMBER = $BUILD_NUMBER'

          echo "[1] - STAGE_NAME = ${env.STAGE_NAME}"
          sh 'echo [2] - STAGE_NAME = $STAGE_NAME'

          echo "Current user is ${env.USER_NAME}"
          echo "Current user id is ${env.USER_ID} type: ${env.USER_ID.class}"
        }
      }

        stage('STAGE-GET-REPO')  {
               
            steps {
              PrintStageName()
          echo "xx STAGE_NAME = ${env.STAGE_NAME}"
          sh 'xx - STAGE_NAME = $STAGE_NAME'
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
            steps { echo "Monitor"  }
        }

    } // end-stages


}

