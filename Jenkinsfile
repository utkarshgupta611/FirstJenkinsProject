pipeline{
    agent any

    stages{

        stage ('Compiling Stage') {
            withMaven(maven : 'MAVEN_HOME') {
                sh'mvn clean compile'
            }
        }

        stage ('Testing Stage') {
            withMaven(maven : 'MAVEN_HOME') {
                sh'mvn test'
            }
        }

        stage ('Deployment Stage') {
            withMaven(maven : 'MAVEN_HOME') {
                sh'mvn deploy'
            }
        }
    }
}