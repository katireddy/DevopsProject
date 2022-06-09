pipeline {
    
	agent any
    stages{
        stage("Clone code from GitHub") {
            steps {
                script {
                    git branch: 'main', url: 'https://github.com/katireddy/NewOne.git';
                }
            }
        }
        
        stage('BUILD'){
            steps {
                sh 'mvn clean install -DskipTests'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }

	    stage('UNIT TEST'){
            steps {
                sh 'mvn test'
            }
        }


        


    }

}

