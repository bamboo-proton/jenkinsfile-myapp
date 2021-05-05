node {
    stage('Source checkout') {
        git branch: 'master',
            credentialsId: 'github-bamboo-proton',
            url: 'https://github.com/bamboo-proton/jenkinsfile-myapp.git'
    }
    stage('List files'){
        sh 'ls'
    }
}
