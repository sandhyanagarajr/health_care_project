pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/sandhyanagarajr/health_care_project/'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with sandhya'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with sandhya'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with sandhya'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with sandhya'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t myimg1 .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8082:8091 --name c001 myimg1'
            }
        }   
    }
}
