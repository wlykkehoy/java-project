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
                sh "echo Hello from Deploy!"
                sh "ls -la"
                sh "ls -la dist"
                sh "aws s3 cp dist/rectangle-${BUILD_NUMBER}.jar s3://lykk3260-seis665-hw10/"
            }
        }
        stage("Report") {
            steps {
                sh "echo Hello from Report!"
            }
        }
    }
}


