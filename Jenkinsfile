node {
    stage('SCM') {
        // Checkout your source code repository
        checkout scm
    }

    stage('SonarQube Analysis') {
        withSonarQubeEnv('SonarQube Server') {
            // Run SonarQube analysis
            sh "mvn clean verify sonar:sonar \
                -Dsonar.projectKey=com.example:expo2.0 \
                -Dsonar.projectName='com.example:expo2.0' \
                -Dsonar.host.url=http://localhost:9020"
        }
    }
}
