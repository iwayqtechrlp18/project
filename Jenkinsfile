pipeline {
	agent any
	   stages{
	   	stage ('stage1') {
	   		steps {

	   			echo 'stage1 completed'
	   		}

	   		
	   	}
	   	stage ('stage2'){

	   		steps{

	   			input('Do you want  to proceed ?')
	   			echo 'stage 2 completed'
	   		}
	   	}
	   	stage ('stage3') {

	   		steps{

	   			echo 'stage3 completed'
	   		}
	   	}
	   }




}
