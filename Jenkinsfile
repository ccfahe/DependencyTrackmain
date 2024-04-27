pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "maven"
    }

    stages {
        stage('Build') {
            steps {
                when {
                    tag "release-*"
                }
               
            }
            stage('test'){
                steps{
                    echo 'Hello'
                }
            }

        }
        
        }
    }

