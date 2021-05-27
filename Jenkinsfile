pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3"
        jdk "JDK11"
    }

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git branch: 'dev',
                    url: 'https://github.com/matthcol/movieapijava2021.git'

                // Run Maven on a Unix agent to compile.
                sh "mvn -Dmaven.test.failure.ignore=true clean"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        }
    }
}
