pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh './mvnw package' 
            }
        }
        
        stage('Test') {
          steps {
            echo 'Testing'
            }
        }  
        
        stage('Package') {
          steps {
            echo 'Packaging'
            }
        }  
        
        stage('Deploy') {
          steps {
            echo 'Deploying'
            }
        } 
    }
    
    post {
    	failure {
        	sh "git bisect start ${5db1dd430cafb6e37dfb6076d125fd1845c699bf} ${ac3e64208e3bcf85eaeff2f870083212f526676f }"
			sh "git bisect run mvn clean test"
			sh "git bisect reset"
    	}
   }

}
