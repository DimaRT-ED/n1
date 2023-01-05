pipeline{
    agent any
    
    environment{
        ONE='one'
    }
    
    stages{
        stage('clone'){
            steps{
                sh  ' pwd '
                echo "STEP1"
            }
        }
        stage('test'){
            steps{
                sh '''
                    hostname
                    echo "STEP2"
                    echo " Build number is : ${BUILD_NUMBER}"
                    echo "ONE = $ONE"
                '''
            }
        }
        stage('build'){
            environment{
              ONE='two'
            }
            steps{
                sh '''
                    hostname
                    echo "STEP3"
                    echo "ONE = $ONE"
                '''
            }
        }
        stage('build2'){            
            steps{
                sh '''
                    echo "STEP4"
                    echo "ONE = $ONE"
                '''
            }
        }
    }
}
