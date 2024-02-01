node {
    docker.image ('node:lts-buster-slim') .inside('-p 3000:3000') {

        stage ('Build') {
            sh 'npm install'
        }
        stage ('Test') {
            sh './jenkins/scripts/test.sh'
        }
        stage ('Manual Approval') {
            input message : 'Lanjutkan ke tahap Deploy? (klik "Proceed" untuk melanjutkan)'
        }
        stage ('Deploy') {
            sh './jenkins/scripts/deliver.sh'
            sleep (time: 60, unit: 'SECONDS')
            //sh './jenkins/scripts/kill.sh'
        }
    }
}