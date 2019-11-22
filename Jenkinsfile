pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
               withAWS(region:'ap-northeast-1',credentials:'AKIA6JWGLDU%UUBCLE5S') {
                    s3Upload(file:'index.html', bucket:'jenkins.bucket.angelo0203', path:'./index.html')
                }
            }
        }
    }
}