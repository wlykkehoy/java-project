pipeline {
    agent {label "linux"}

    stages {
        stage("Unit Tests") {
            steps {
                sh "echo Hello from Unit Tests!"
                // sh "ant -buildfile test.xml"
                // git credentialsId: 'b3facc86-2272-494b-a315-4b393331cae1', url: 'https://github.com/wlykkehoy/java-project-private'
            }
        }
        stage("Build") {
            steps {
                sh "echo Hello from Build!"
            }
        }
        stage("Deploy") {
            steps {
                sh "echo Hello from Deploy!"
            }
        }
        stage("Report") {
            steps {
                sh "echo Hello from Report!"
            }
        }
    }
}


