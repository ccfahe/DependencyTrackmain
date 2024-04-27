pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "maven"
    }

    stages {
        stage('Build') {
            steps {
                when {buildingTag()}
               
            }

        }
         stage('Dependency Track Upload') {
            steps {
                echo "Test"
                //dependencyTrackPublisher artifact: 'target/bom.xml', autoCreateProjects: true, dependencyTrackApiKey: 'deptrack', dependencyTrackFrontendUrl: '', dependencyTrackUrl: 'http://192.168.1.2:8888/', overrideGlobals: true, projectId: '5c7f470a-d554-4a95-8e17-f79f976d2e44', synchronous: true
            }
        }
    }
}
