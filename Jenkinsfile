pipeline{
	agent any 
	stages{
		stage ('Maven Build'){

			steps{

				echo 'Completed'
				sh '/root/apache-maven-3.5.4/bin/mvn package'
				archiveArtifacts '*.war'
			}
		}
		stage ('SonarQube Scanner'){

			steps{

				echo 'SonarQube is  completed'
				withSonarQubeEnv('sonar6') {
   sh '/root/apache-maven-3.5.4/bin/mvn sonar:sonar'
}
			}
		}
		stage ('Artifactory'){
			steps{

				script{
				def server = Artifactory.server 'jfrog'
				def uploadSpec = """{
  "files": [
    {
      "pattern": "target/*.war",
      "target": "libs-release"
    }
 ]
}"""
server.upload(uploadSpec)
def buildinfo = server.upload uploadSpec
server.publishBuildInfo buildinfo
}
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
