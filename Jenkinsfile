pipeline{
    agent any

    tools{
        maven "MAVEN_HOME"
    }

    stages{

        stage ('Building Stage') {
            steps {
                // bat'mvn clean compile'
                bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }
            }
        }

        stage ('Testing Stage') {
           steps {
                withMaven(maven : 'MAVEN_HOME') {
                bat "mvn test"
            }
           }
        }

        stage ('Deployment Stage') {
           steps{
                withMaven(maven : 'MAVEN_HOME') {
                // bat'mvn deploy'
                bat "mvn -Dmaven.test.failure.ignore=true deploy"
            }
           }
        }
    }
}