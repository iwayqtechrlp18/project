pipeline{
	agent any 
	stages{
		stage ('Maven Build'){

			steps{

				echo 'Completed'
				sh '/root/apache-maven-3.5.4/bin/mvn package'
			}
		}
		stage ('SonarQube Scanner'){

			steps{

				echo 'SonarQube is  completed'
				withSonarQubeEnv('sonar6') {
   sh 'mvn sonar:sonar'
}
			}
		}
		stage ('Artifactory'){

			steps{

				echo 'Completed'
			}
		}
		stage('Deploy to Test'){

			steps{

				echo 'Completed'
			}
		}
		stage('Test Results'){

		steps{

			echo 'Completed'
		}
		}
		stage('Approvals'){

			steps{

				input('Do you want  to proceed?')
			}
		}
		stage('Deploy to Production'){

			steps{

				echo 'completed'
			}
		}






	}












}
