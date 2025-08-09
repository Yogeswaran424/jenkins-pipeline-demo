pipeline {
    agent any

    // run weekly: H H * * 0  -> every Sunday once (approx every 7 days)
    triggers {
        cron('H H * * 0')
    }

    stages {
        stage('Checkout') {
            steps {
                // if job uses Pipeline script from SCM, checkout scm will use the job's SCM
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Building..."
                sh 'echo build step: listing files; ls -la || dir'
            }
        }

        stage('SmokeTest') {
            steps {
                echo "Running smoke test..."
                // Simulate a simple test
                sh 'test -f hello.txt && echo "hello.txt exists" || (echo "file missing" && exit 1)'
            }
        }

        stage('Success') {
            when { expression { currentBuild.resultIsBetterOrEqualTo(hudson.model.Result.SUCCESS) } }
            steps {
                echo "Pipeline succeeded"
            }
        }
    }

    post {
        success {
            echo "Post: SUCCESS"
        }
        failure {
            echo "Post: FAILURE — collect logs"
        }
    }
}
