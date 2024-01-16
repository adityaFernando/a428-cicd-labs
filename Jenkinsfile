node {
    docker.image ('node:lts-buster-slim') .inside('-p 3000:3000') {

        stage ('Build') {
            sh 'npm install'
        }
        stage ('Test') {
            sh './jenkins/scripts/test.sh'
        }
        stage ('Deploy') {
            sh './jenkins/scripts/delivery.sh'
            input message : 'Sudah selesai menggunakan React App? (klik "Proceed" untuk mengakhiri)'
            sh './jenkins/scripts/kill.sh'
        }
    }
}