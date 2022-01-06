pipeline{
    agent any

    stages{

        stage ('Compiling Stage') {
            steps {
                withMaven(maven : 'MAVEN_HOME') {
                bat'mvn clean compile'
            }
            }
        }

        stage ('Testing Stage') {
           steps {
                withMaven(maven : 'MAVEN_HOME') {
                bat'mvn test'
            }
           }
        }

        stage ('Deployment Stage') {
           steps{
                withMaven(maven : 'MAVEN_HOME') {
                bat'mvn deploy'
            }
           }
        }
    }
}