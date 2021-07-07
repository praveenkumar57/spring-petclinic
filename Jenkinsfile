pipeline {
     agent any
     stages {
       stage('SCM') {
        steps {
         git 'https://github.com/GitPracticeRepo/spring-petclinic.git'
        }
      }
       stage ('build the packages') {
         steps {
	  sh 'mvn clean package'
          }
       }
      stage ('archival') {
        steps {
	 archive 'target/*.jar'
      }
    }
  }
}
