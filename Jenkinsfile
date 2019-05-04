node('MVN'){
    
    stage('GIT'){
        git branch: 'Dev', url: 'https://github.com/GitPracticeRepo/spring-petclinic.git'
    }
    stage('Build'){
        sh 'mvn package'
    }
	stage('Archive'){
		archive 'target//*.jar'
		junit 'target/surefire-reports/*.xml'
	}
	stage('sonar') {
		withSonarQubeEnv('sonarcube') {
			// requires SonarQube Scanner for Maven 3.2+
			sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.2:sonar'
		}
	}
}