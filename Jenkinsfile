pipeline {
    agent {
          label 'AGENT1'
    }
    options{
         timeout (time: 10 , unit: 'SECONDS')
    }
    stages{
        stage('Build'){
             steps{
                  sh 'echo  this is build'
                  sh 'sleep 10'

             }

        }
        stage('Test'){
        
        steps{
              
              sh 'echo this is test'

        }
        }
        stage('Deploy'){
            steps{
                 
                  sh 'echo this is deploy'
                  

            }

        }
    }

    post{
        always{
            echo ' this section runs always'
        }
        success{
            echo 'this section runs only after success'
        }
        failure{
            echo 'this section runs if build fail'
        }
    }
}