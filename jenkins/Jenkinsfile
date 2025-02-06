pipeline{
    agent {
        label 'dev-server'
    }

    tools {
        maven 'test-maven'
    }
    
    stages{

        stage('build stage'){
            steps{
                sh 'mvn -B -DskipTests clean package'
            }
            post {
              success {
                    archiveArtifacts artifacts: '**/target/*.war'
                  }
            }            
        }
    }
}
