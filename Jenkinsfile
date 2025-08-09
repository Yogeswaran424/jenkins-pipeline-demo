pipeline {
    agent any
    stages {
        stage('Broken') {
            steps {
                echo "this will break"
            } // <-- accidentally remove this closing brace or add invalid code
        