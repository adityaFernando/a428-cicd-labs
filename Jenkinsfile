node {
    docker.image ('node:lts-bustes-slim') .inside('-p 3000:3000') {

        stage ('Build') {
            sh 'npm install'
        }
        stage ('Test') {
            sh './jenkins/scripts/test.sh'
        }
    }
}