pipeline {
    agent any
    stages {
        stage('Source Code Checkout') {
            steps {
                echo 'Angular Test Project GitHub Repository Code Checkout'
                git 'https://github.com/intazar/jenkins-test'
                
            }
        }
        stage('Install Node Modules') {
            steps {
                echo 'Angular Test Project npm Install'
                sh "npm install"
            }
        }
        stage('Testing Stage') {
             steps {
                echo 'Angular Test Project Code Unit Testing Stage'
                sh "npm run test-headless"
            }
         }
       
        stage('Make Prod Build') {
            steps {
                echo 'Angular Test Project Prod Build'
                sh "npm run build --prod"
            }
        }
       stage('Deploy Application with Tomcat Server' ) {
            steps {
                echo 'Angular Test Project Deployement with Tomcat Server'
				sh "cp -a /var/lib/jenkins/workspace/angular-pipeline/dist/jenkins-test/. /var/www/angular-app/html/"
            }
        }
    }
}
