// SEIS665 - Homework #10
// Author: Wade Lykkehoy

pipeline {
    
    agent {label "linux"}

    stages {
        stage("Unit Tests") {
            steps {           
                sh "ant -f test.xml"
                junit "reports/result.xml"
            }
        }
        stage("Build") {
            steps {
                sh "ant -f build.xml -v"
            }
        }
        stage("Deploy") {
            steps {
                sh "aws s3 cp dist/rectangle-${BUILD_NUMBER}.jar s3://lykk3260-seis665-hw10/"
            }
        }
        stage("Report") {
            steps {
                withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'c4f40f95-44cb-488e-a749-121f7346a15d', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
                    sh "aws cloudformation describe-stack-resources --region us-east-1 --stack-name jenkins"
                }
            }
        }
    }
}


