pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        
        stage('second stage') {
            steps {
                script {
                sh'''
                touch amrutha.txt
                cat amrutha.txt
                ls -l
                mkdir prajju
                ls -l
                pwd
                echo 'Finishing my stage'
                '''
                }
            }
        }
                
        stage ('third stage') {
            steps {
                echo 'finishing my third stage'
                        sh '''
                        rm amrutha.txt
                        rmdir prajju
                        echo 'third stage'
                        touch log.txt
                        touch log.csv
                        touch results.txt
                        '''
                    }
                }
                
    }
    post{
        always{
            archiveArtifacts artifacts: 'log.txt,log.csv,results.txt', followSymlinks: false
        }
    }
    
}