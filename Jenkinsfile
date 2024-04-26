pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "maven"
    }

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/ccfahe/DependencyTrackTest.git'

                // Run Maven on a Unix agent.
                sh "mvn -Dmaven.test.failure.ignore=true clean package"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }

        }
         stage('Dependency Track Upload') {
            steps {
                dependencyTrackPublisher artifact: 'target/bom.xml', autoCreateProjects: true, dependencyTrackApiKey: 'deptrack', dependencyTrackFrontendUrl: '', dependencyTrackUrl: 'http://192.168.1.2:8888/', overrideGlobals: true, projectId: '5c7f470a-d554-4a95-8e17-f79f976d2e44', synchronous: true
            }
        }
    }
}
