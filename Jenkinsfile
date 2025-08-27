pipeline{
    agent{
        docker{
            image "cypress/browsers:latest"
            args "entrypoint="
        }
    }
    stages{
        stage('installation'){
            steps{
                sh 'npm i'
            }
        }
        stage('run tests'){
            steps{
                sh 'npx cypress run'
            }
        }
    }
    // post{
    //     always{
    //         node cucumber-report-generator.js
    //         archiveArtifacts artifacts: 'rapports/**'
    //     }
    // }
}