pipeline {
    agent {
        docker {
            image 'maven:3.9.3-eclipse-temurin-17'
            args '-v $HOME/.m2:/root/.m2'
        }
    }
 
    stages {
        stage('Checkout') {
            steps {
                // Get some code from a GitHub repository
                git branch: 'main', url: 'https://github.com/AnissaBOUNAB/my-app.git'
            }
        }
        stage('Build') {
            steps {
                // Run Maven on a Unix agent.
                sh "mvn -DskipTests clean package"
            }
        }
        stage('Test') {
            steps {
                // Run Maven on a Unix agent.
                sh "mvn test"
            }
        }    
        stage('Deploy') {
            steps {
                // Run Maven on a Unix agent.
                echo "Artifact deployed"
            }
        }          
    }
}
