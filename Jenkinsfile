pipeline {
    agent any

    tools {
        maven 'MAVEN_HOME'   // must match name in Manage Jenkins → Tools
    }

    stages {
        stage('git repo & clean') {
            steps {
                bat "rmdir /s /q mavenjava || exit 0"
                bat "git clone https://github.com/snigdhapaluri/mavenjava.git"
                bat "mvn clean -f mavenjava"
            }
        }

        stage('install') {
            steps {
                bat "mvn install -f mavenjava"
            }
        }

        stage('test') {
            steps {
                bat "mvn test -f mavenjava"
            }
        }

        stage('package') {
            steps {
                bat "mvn package -f mavenjava"
            }
        }
    }
}

