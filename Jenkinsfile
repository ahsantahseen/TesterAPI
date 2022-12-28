pipeline {
    agent any
    triggers {
       githubPush()
    }

    stages {
        stage('Git'){
            steps{
                git 'https://github.com/ahsantahseen/TesterAPI.git'
            }
        }
        stage('Build'){
            steps{
                sh 'npm install'
            }
        }
        stage('Run'){
            steps{
                sh 'node index.js'
            }
        }
    }
    post{
        success {
            mail to: "cs1912297@szabist.pk",
            subject: "Build Notification",
            body: "Test Build Successful"
        }
        failure {
            mail to: "cs1912297@szabist.pk",
            subject: "Build Notification",
            body: "Test Build Failed"
        }
    }
}
