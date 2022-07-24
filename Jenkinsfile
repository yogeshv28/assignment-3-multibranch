pipeline {
    agent any

    stages {
        stage('SCA') {
            agent
            {
                label 'windows'
            }
            steps {
                echo 'Steps to perform Static Code Analysis'
            }
        }
        stage('Unit Tests') {
            steps {
                echo 'Steps to execute Unit Tests'
            }
        }
        stage('Build') {
            steps {
                echo 'Steps to execute build commands'
            }
        }
        stage('Docker Image') {
            steps {
                echo 'Steps to create Docker Image'
            }
        }
        stage('Scan Docker Image') {
            options {
                skipDefaultCheckout()
            }
            steps {
                echo 'Steps to Scan Docker Image'
            }
        }
        stage('Deploy to Dev Cluster') {
            when {
                branch 'dev'
            }
            steps {
                echo "Steps to deploy application to ${BRANCH_NAME} minikube cluster"
            }
        }        
        stage('Deploy to Staging Cluster') {
            when {
                branch 'staging'
            }
            steps {
                echo "Steps to deploy application to ${BRANCH_NAME} minikube cluster"
            }
        }
        stage('Deploy to Prodction Cluster') {
            when {
                branch 'main'
            }
            steps {
                echo "Steps to deploy application to ${BRANCH_NAME} minikube cluster"
            }
        }        
    }
    post {
        always {
            echo "Steps to publish Unit Tests results"
        }
    }
}
