node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'Default Maven';
    withSonarQubeEnv() {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=com.example:expo2.0 -Dsonar.projectName='com.example:expo2.0 -Dsonar.host.url=http://localhost:9020/'"
    }
  }
}
