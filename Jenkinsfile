pipeline {
	agent any
	
	stages {
		stage('Compile Stage') {
			steps {
				withMaven(maven : 'default') {
					sh 'mvn clean compile'
				}
			}
		}
		stage('Testing Stage') {
			steps {
				withMaven(maven : 'default') {
					sh 'mvn test'
				}
			}
		}
		stage('SonarQube Stage') {
			steps {
				withMaven(maven : 'default') {
					sh 'mvn sonar:sonar'
				}
			}
		}
		/*stage('Deployment Stage') {
			steps {
				withMaven(maven : 'default') {
					sh 'mvn deploy'
				}
			}
		}*/
	}
}