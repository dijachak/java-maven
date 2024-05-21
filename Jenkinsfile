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
        stage('Run') {
            steps {
                // Run the packaged JAR file
                script {
                    dir('maven') {
                        sh 'java -jar target/maven-0.0.1-SNAPSHOT.jar'
                    }
                }
            }
        }
    }
}
