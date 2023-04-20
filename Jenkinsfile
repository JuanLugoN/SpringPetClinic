pipeline {
    agent{
        label 'master'
    }

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3"
    }

    stages {
        stage('Checkout'){
            steps {
                git branch: 'main', url: 'https://github.com/JuanLugoN/SpringPetClinic.git'
            }
        }
        stage('Build') {
            steps{
                sh 'mvn compile'
            }
        }
        stage('Test') {
            steps{
                sh 'mvn test'
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
        stage('Deplor') {
            steps{
                sh 'java -jar /var/lib/jenkins/workspace/PetClinicDeclarativePipeline/target/*.jar'
            }
        }
    }
}
