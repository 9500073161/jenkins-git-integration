node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'M2_HOME';
    withSonarQubeEnv() {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=Maven-Sonarqube-auto -Dsonar.projectName='Maven-Sonarqube-auto'"
    }
  }
}
