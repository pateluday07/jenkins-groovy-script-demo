pipeline{

	agent any
	
	stages{
	    
	    stage('github pull'){
			steps{
				echo "pulling code from github repo";
				git 'https://github.com/pateluday07/jenkins-groovy-script-demo.git'
			}
		}
	
		stage('clean'){
			steps{
				bat "clean.bat"
			}
		}
		
		stage('test'){
			steps{
				bat "test.bat"
			}
		}
		
		stage('build'){
			steps{
				bat "build.bat"
			}
		}
		
	}
	
	post {
		
		always{
			echo 'This will always run'
		}
		
		success{
			echo 'This will run on success'
		}
		
		failure{
			echo 'This will run on failure'
		}
		
		unstable{
			echo 'This will run if the build is unstable'
		}
		
		changed{
		 echo 'This will only run if the state of the pipeline changed'
		 echo 'for example if the previous pipeline failed and current one is success and vice versa'
		}
	}	
}
