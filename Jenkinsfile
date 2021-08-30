pipeline {
  agent any
  stages {
    stage('Build Docker'){
        steps{
          sh """
          docker run -d --name nginx-test -p 58080:80 \
          --mount type=bind,source=`pwd`/conf,target=/etc/nginx/conf.d \
          --mount type=bind,source=`pwd`/html,target=/usr/share/nginx/html \
          nginx
          """
        }
    }
  }            
}
