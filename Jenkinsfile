pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'rm -rf Build'
                sh 'mkdir Build'
                sh 'touch Build/Car.txt'
                sh 'echo "chassis" >> Build/Car.txt'
                sh 'echo "engine" >> Build/Car.txt'
                sh 'echo "body" >> Build/Car.txt'
            }
        }
        stage ('Test') {
            steps {
                sh 'test -f Build/Car.txt'
                sh 'grep "chassis" Build/Car.txt'
                sh 'grep "engine" Build/Car.txt'
                sh 'grep "body" Build/Car.txt'
            }
        }
        stage ('Publis') {
            steps {
                archiveArtifacts artifacts: 'Build/'
            }
        }
    }
}
