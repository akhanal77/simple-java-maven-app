pipeline {
    agent any

    tools
   {
    maven 'm399'
    jdk 'jdk21'
   }
<<<<<<< HEAD
=======

    
>>>>>>> 9f034c8497d8bdec274d4cff53a756060a0d7a0d
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') { 
            steps {
                sh './jenkins/scripts/deliver.sh' 
            }
        }
    }
}
