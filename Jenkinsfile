pipeline { 
  
   agent { label 'slave' }
   tools {nodejs "nodejs"}

   

   stages {
     stage ('git clone') {
            steps{
                 sh 'rm -rf zod'
                 sh 'git clone https://github.com/lakshmirj/zod.git'
            }
        }
    stage('Install Dependencies') { 
        steps { 
           sh 'npm install -g serverless'
           
        }
     }    
   
     
     stage ('install serverless'){
            steps {
                sh 'curl -o- -L https://slss.io/install | bash'
                sh 'curl -o- -L https://slss.io/install | VERSION=2.21.1 bash'
                
                sh 'cd /var/tmp/jenkins/workspace/zodiac/zod && npm install -g serverless && serverless plugin install --name serverless-s3-sync && serverless deploy'
                
                
                
            }
        }

  
   	}

}
