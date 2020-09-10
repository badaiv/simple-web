pipeline {
    agent any
    parameters {
        string(name: 'URL', defaultValue: '127.0.0.1:8080', description: 'URL to check')
    }
    triggers {
        cron('*/5 * * * *') // every 5 mins
    }
    stages {
        stage('Build') {
            steps {
                echo 'Cheking $URL..'
                sh 'curl -s $URL | grep server2 && exit 1 || echo "good!"'
            }
        }
    }
}