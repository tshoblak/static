pipeline {
  agent any
  stages {

    stage('Validate HTML') {
      steps {
        ssh 'tidy -q -e *.html'
      }
    }
    
    stage('Upload to AWS') {
      steps {
        withAWS(region:'us-east-2', credentials:'aws-static') {
            s3Upload(file:'index.html', bucket:'mu-jenkins-repo', path:'index.html')
        }




      }
    }

  }

}
