pipeline {
  agent any
  stages {
    stage('Build Docker'){
        steps{
          sh """
          docker run -d --name nginx-test -p 58080:80 \
          -v `pwd`/conf:/etc/nginx/conf.d \
          -v `pwd`/html:/usr/share/nginx/html \
          nginx
          """
        }
    }
  }            
}
