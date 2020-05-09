pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'echo "Hello World!"'
        sh '''
          echo "Multiline shell steps works too"
          ls -lah
        '''
      }
    },
    stage('Upload to AWS') {
      steps {
        withAWS(region:'us-east-2') {
            s3Upload(file:'index.html', bucket:'mu-jenkins-repo', path:'index.html')
        }


      }
    }
  }

}
