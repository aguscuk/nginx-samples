pipeline {
  agent any
  stages {
    stage('Build Docker'){
        steps{
          sh """
          docker rm -f nginx-test
          docker run -d --privileged --name nginx-test -p 58080:80 \
          -v $pwd/conf:/etc/nginx/conf.d \
          -v $pwd/html:/usr/share/nginx/html \
          nginx
          """
        }
    }
  }            
}
