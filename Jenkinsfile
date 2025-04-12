pipeline {
    agent {
          label 'AGENT1'
    }
    options{
        /* timeout (time: 10 , unit: 'SECONDS')*/
         disableConcurrentBuilds()
    }
    parameters{
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')

        
    }
    stages{
        stage('Build'){
             steps{
                  sh 'echo  this is build'
                  /*sh 'sleep 10' */

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
        stage('print params'){
            steps{
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
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