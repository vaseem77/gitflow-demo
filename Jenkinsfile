pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Pull Code') {
            steps {
                echo 'Pulling code from develop branch...'
                git branch: 'develop',
                    url: 'https://github.com/vaseem77/gitflow-demo.git'
            }
        }

        stage('Copy to Folder') {
            steps {
                echo 'Copying content to target folder...'
                sh 'mkdir -p /tmp/pulled-code'
                sh 'cp -r * /tmp/pulled-code/'
                echo 'Code pulled successfully!'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
