pipeline {
  agent any
  stages {
    stage('Install') {
      parallel {
        stage('app') {
          environment {
            DEBUG = 'false'
          }
          steps {
            echo 'Instalando dependencias...'
            sh 'sleep 10'
            sleep 45
          }
        }

        stage('3-part') {
          steps {
            echo 'Instalando dependencias de 3ro...'
            sh 'apt update'
            sleep 15
          }
        }

        stage('db') {
          steps {
            echo 'Instalando base de datos...'
            sh '''echo "instalando mysql-server"
                # apt install -y mysql-server'''
            sleep 30
          }
        }

      }
    }

    stage('Build') {
      steps {
        echo 'construyendo app...'
      }
    }

  }
  environment {
    NODE_ENV = 'development'
    NODE_APP = 'notis'
    DB_NAME = 'test'
    DB_PORT = '27017'
  }
}