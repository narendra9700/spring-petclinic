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
}