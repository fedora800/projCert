def PrintStageName() {
  echo '-----------------${STAGE_NAME}-----------------'
}

pipeline {

   agent { label 'linux-agents' }

   stages {

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

