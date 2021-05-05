@Library('eigi-jenkins-library') _

def notify = new common.v1.Notify(this)

node {
    stage('Source checkout') {
        git branch: 'master',
            credentialsId: 'github-bamboo-proton',
            url: 'https://github.com/bamboo-proton/jenkinsfile-myapp.git'
    }
    stage('List files'){
        sh 'ls'
    }
    stage('Build'){
        withMaven(maven: 'Maven 3.6.3', jdk: 'JDK 11') {
            sh 'mvn clean install'
        }
    }
    stage('Notify'){
       notify.googleChat("${JOB_NAME} ${currentBuild.currentResult} #${BUILD_NUMBER} <${env.BUILD_URL}|View Build>","https://chat.googleapis.com/v1/spaces/AAAAZDaMU-c/messages?key=AIzaSyDdI0hCZtE6vySjMm-WEfRq3CPzqKqqsHI&token=_f0TY-_2IDQ8CQz0cYmNc6VASJqfFaMzxeloqcBSVAs%3D&threadKey=jenkins")
    }
}
