pipeline {
  agent any
  stages {
    stage('Build Docker'){
        steps{
          sh """
          hostname
          docker rm -f nginx-test
          docker run -d --name nginx-test -p 58888:80 \
          -v `pwd`/conf:/etc/nginx/conf.d \
          -v `pwd`/html:/usr/share/nginx/html \
          nginx
          docker exec nginx-test ls -ltrha /usr/share/nginx/html
          docker exec nginx-test ls -ltrha /etc/nginx/conf.d
          """
        }
    }
  }            
}
