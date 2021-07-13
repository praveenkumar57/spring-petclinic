pipeline {
    agent any
    parameters {
        string defaultvalue: 'master', name: 'mybranch'
    }
    stages {
       stage('SCM') {
        steps {
                git branch: "${params.mybranch}",url:https://github.com/GitPracticeRepo/spring-petclinic.git'
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
