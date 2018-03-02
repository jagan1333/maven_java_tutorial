pipeline {
    agent any
    
    stages {
        stage ('Initialize') {
            steps {
                
                 sh 'echo "PATH = %PATH%"'
                 sh 'echo "M2_HOME = %M2_HOME%"'
            }
        }

        stage ('Build') {
            steps {
                    sh 'cd NumberGenerator & mvn clean install'
            }
             post {
                success {
                    junit 'NumberGenerator/target/surefire-reports/*.xml'
                        }
                 }
               

           
            }
        }
    
}
