pipeline {
    agent {
            label 'win11'
    }
    tools {
        maven 'mvn'
    }   
    stages {
        stage ('Clean') {
            steps {
                bat 'mvn clean'
            }
        }
        stage ('Test') {
            steps {
                bat 'mvn test'
            }
        }
        stage ("misc") {
            parallel {
                stage ('Compile') {
                    steps {
                        bat 'mvn install'
                        echo "installed"
                    }
                }
                stage ('static analysis') {
                    steps {
                        withSonarQubeEnv('def') {
                            bat 'mvn sonar:sonar -Dsonar.host.url=http://localhost:9000 -Dsonar.projectkey=hello_world -Dsonar.java.binaries=target'
                        }
                    }
                }
            }
        }
    }
    post {
        success {
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true, followSymlinks: false
            junit allowEmptyResults: true, keepLongStdio: true, keepProperties: true, testResults: 'target/surefire-reports/*.xml'
        }
        //fixed {
            //emailext attachLog: true, body: '', subject: 'Hello world is fixed, well done !', to: 'corentin.noel56@gmail.com'
        //}
        //failure {
            //emailext attachLog: true, body: '', subject: 'Hello world is broken, boohoo !', to: 'corentin.noel56@gmail.com'
        //}
    }
}
