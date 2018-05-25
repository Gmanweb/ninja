// node('docker') {
// node {

//     checkout scm

//     stage('Build') {
//         docker.image('maven:3.3.3').inside {
//             sh 'mvn --version'
//         }
//     }

// }

pipeline {
    agent {
        docker {
            image 'maven:3-alpine' 
            args '-v /root/.m2:/root/.m2' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
    }
}
