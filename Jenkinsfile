def PrintStageName() {
  echo '-----------------${env.STAGE_NAME}-----------------'
}

pipeline {

   agent { label 'linux-agents' }

   stages {

      stage("List env vars"){
        steps{
          sh "printenv | sort"
        }
      }
  
      stage("Using env vars"){
        steps{
          echo "BUILD_NUMBER = ${env.BUILD_NUMBER}"
          sh 'echo the BUILD_NUMBER = $BUILD_NUMBER'
  
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
            steps { echo "Monitor"  }
        }

    } // end-stages


}

