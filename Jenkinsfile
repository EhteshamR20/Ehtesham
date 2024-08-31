pipeline {
    agent any  // This means the pipeline can run on any available agent

    environment {
        // Define environment variables if needed
        SONARQUBE_SERVER = 'SonarQube'  // The name of the SonarQube server configuration in Jenkins
        SLACK_CHANNEL = '#your-channel'  // Your Slack channel
    }

    stages {
        stage('Git Clone') {
            steps {
                echo 'Cloning the repository...'
                // Git repository URL
                git url: 'https://github.com/betawins/VProfile-1.git'
            }
        }

        // stage('SonarQube Analysis') 
        //     steps {
        //         script {
        //             echo 'Performing SonarQube analysis...'
        //             // Ensure SonarQube Scanner is installed and configured in Jenkins
        //             withSonarQubeEnv(SONARQUBE_SERVER) {
        //                 // Run SonarQube analysis (adjust according to your setup)
        //                 sh 'mvn sonar:sonar -Dsonar.projectKey=your_project_key'
        //             }
        //         }
        //     }
        // }

        // stage('Slack Notification') {
        //     steps {
        //         script {
        //             echo 'Sending Slack notification...'
        //             // Send notification to Slack (ensure Slack plugin is configured)
        //             slackSend channel: SLACK_CHANNEL, message: 'Build completed successfully!'
        //         }
        //     }
        // }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
        always {
            echo 'Pipeline finished.'
        }
    }
}
