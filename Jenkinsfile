pipeline {
  agent any
  stages {
    stage('Checkout the Code') {
      steps {
        git(url: 'https://github.com/AOKingsax/deno-app-with-docker', branch: 'main')
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t royalkingsax/denoapp:latest .' 
      }
    }

    stage('Log into Dockerhub') {
      steps {
        sh 'docker login -u $DOCKERHUB_USER -p $DOCKERHUB_PASSWORD'
      }
    }

    stage('Push to DockerHub') {
      steps {
        sh 'docker push royalkingsax/denoapp:latest'
      }
    }

  }
}