pipeline {
    agent any
    stages {
        stage('Lint HTML') {
            steps {
                    sh 'echo "Start tidy the html"'
                    sh 'tidy -q -e *.html'                 
                 }
            }

        stage('Upload to AWS') {
            steps {
                    withAWS(region:'ap-northeast-1',credentials:'aws-static') {
                      sh 'echo "Start upload the index.html to S3"'
                    s3Upload(file:'index.html', bucket:'jenkins.bucket.angelo0203', path:'index.html')
                 }
            }
        }
    }
}