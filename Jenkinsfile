pipeline {
  agent any
  stages {
    stage('Upload to AWS') {
      steps {
        ssh 'tidy -q -e *.html'
      
        withAWS(region:'us-east-2', credentials:'aws-static') {
            s3Upload(file:'index.html', bucket:'mu-jenkins-repo', path:'index.html')
        }




      }
    }
  }

}
