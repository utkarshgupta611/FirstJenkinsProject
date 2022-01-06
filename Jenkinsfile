pipeline{
    agent any

    stages{

        stage ('Compiling Stage') {
            steps {
                withMaven(maven : 'MAVEN_HOME') {
                // bat'mvn clean compile'
                bat "mvn -Dmaven.test.failure.ignore=true clean compile"
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