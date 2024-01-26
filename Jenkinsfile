pipeline {
    agent any
    parameters {
        string(name: 'Prajval', defaultValue: '')
    }

    stages {
        stage('Hello') {
            when {
                expression{
                "${params.condition}" == True
                }
            }
            steps {
                echo 'Hello World'
                echo "${params.Prajval}"
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