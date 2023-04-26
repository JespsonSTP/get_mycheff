pipeline {
    agent any //selecting agents that we created
    stages {
        //this is where we will declare each steps of our pipeline
        stage("Clone Repo"){
            steps {
                sh "git clone "
            }
        }
        stage("Build"){
            steps {
                dir(""){
                    sh "mvn clean install"
                }
            }
        }
        stage("Test"){
            steps {
                dir(""){
                    sh "mvn test"
                }
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
    }
}