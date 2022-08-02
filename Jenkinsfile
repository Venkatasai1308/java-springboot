pipeline {
    // where or who
    agent any
    
    // collection of stages
    stages{
        stage('Quality Dpt'){
            steps{
                sh 'mvn test -B'
            }
        }
        stage('Package '){
            steps{
                sh 'mvn clean package -B -Dmaven.test.skip=true'
            }
        }
        stage('Deploy war'){
            steps{
                sh 'cp target/bermtec-0.0.1.war /var/lib/tomcat8/webapps/bermtec-0.0.1.war'
            }
        }
    }
    post{
        failure{
            echo 'You failed'
        }
        success{
            echo 'You are Yoda'
        }
    }
}