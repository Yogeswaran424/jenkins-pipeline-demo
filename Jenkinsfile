pipeline {
    agent any

    // Weekly schedule: Runs every Sunday at a random time
    triggers {
        cron('H H * * 0')
    }

    stages {

        stage('Checkout') {
            steps {
                echo "===== Checking out the repository ====="
                // Jenkins job should be configured with "Pipeline script from SCM"
                // so 'checkout scm' will pull from your GitHub repo automatically.
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "===== Building the project ====="
                // Dummy build step - replace with actual build commands
                sh 'echo "Build step complete"'
            }
        }

        stage('Test') {
            steps {
                echo "===== Running tests ====="
                // Simulate test execution
                sh 'test -f hello.txt && echo "hello.txt exists" || (echo "file missing" && exit 1)'
            }
        }

        stage('Deploy') {
            steps {
                echo "===== Deploying application ====="
                // Dummy deployment step
                sh 'echo "Deploy step complete"'
            }
        }
    }

    post {
        success {
            echo "🎉 Pipeline completed successfully!"
        }
        failure {
            echo "❌ Pipeline failed — please check logs."
        }
        always {
            echo "📦 Pipeline run finished at: ${new Date()}"
        }
    }
}
