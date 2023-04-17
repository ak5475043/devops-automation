pipeline{
    agent any
    tools{
        maven 'maven3.5.0'
            
    }
    stages{
        stage('build maven'){
            steps{
                
            sh 'mvn clean install'
            }
        }
        stage('build docker image'){
            steps{
            
                sh 'sudo docker build -t ayush2107/devops-integration:1.0 .'
                
            }
        }    
        stage('push image to hub'){
            steps{
                sh 'sudo docker login -u ayush2107 -p urhacked21'
                sh 'sudo docker push ayush2107/devops-integration:1.0'
            }
        }
        stage('pull image from hub'){
           steps{
               sh 'sudo ssh -i "MyKeyPair.pem" ubuntu@ec2-18-233-9-217.compute-1.amazonaws.com -yes'
               sh 'sudo docker run -it -d -p 9090:8080 ayush2107/devops-integration:1.
           }
       }    
    }
    
}
