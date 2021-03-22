pipeline {
   agent {
     label 'ubuntuserver'
}
 parameters {
   choice (
     name: 'mybranch',
     choices: ['master','Dev','Test'],
     description: 'passing the branch'
  )
  }

  stages {
   stage('git') {
    steps {
      git branch: "${params.mybranch}" ,url: 'https://github.com/praveenkumar57/spring-petclinic.git'
}
 
    stage('build the code') {
       when {
        expression {
          params.mybranch == 'master'
       }
     }
    steps {
       sh 'mvn package'
    }
 }
  stage ('build the code') {
    when {
      expression {
          params.mybranch != 'master'
    }
   }
   steps {
    sh 'mvn clean package'
   }

   }

}



}
