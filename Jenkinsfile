pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the Git repository
                git branch: 'main', url: 'https://github.com/khadijachakkour/java-maven.git'
            }
        }
        stage('Build') {
            steps {
                // Here, we can run Maven commands
                script {
                    // Navigate to the directory containing the Maven project
                    dir('maven') {
                        // Run Maven commands
                        sh 'mvn clean test package'
                    }
                }
            }
        }
    }
}
