pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World from Jenkinsfile'
            }
        }
        stage('Git Branch') {
            steps {
                echo $GIT_BRANCH
            }
        }
    }
}
