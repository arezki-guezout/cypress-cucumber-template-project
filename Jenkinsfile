pipeline{
    agent{
        docker{
            image "cypress/browsers:latest"
            args "--entrypoint="
        }
    }
    stages{
        stage('installation'){
            steps{
                sh 'npm ci'
            }
        }
        stage('run tests'){
            steps{
                sh 'npx cypress run'
            }
        }
    }
    post{
        always{
            sh 'chmod +x bashs/generate_rapport.sh'
            sh './bashs/generate_rapport.sh'
            archiveArtifacts 'rapports/**/*.*'
            cuc
        }
    }
}