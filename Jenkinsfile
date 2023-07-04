
pipeline {

   agent { label 'linux-agents' }

   stages {

        stage('Get-Repo')  {
            steps {
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
        stage("Monitor") {
            steps { echo "Monitor"  }
        }

    } // end-stages


}

