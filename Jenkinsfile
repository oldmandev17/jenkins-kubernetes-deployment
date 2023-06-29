// pipeline {

//   environment {
//     dockerimagename = "oldmandev17/react-app"
//     dockerImage = ""
//   }

//   agent any

//   stages {

//     stage('Checkout Source') {
//       steps {
//         git url 'https://github.com/oldmandev17/jenkins-kubernetes-deployment.git', branch: 'main',
//         credentialsId: 'github-credentials'
//         // echo 'checkout source the application...'
//       }
//     }

//     stage('Build image') {
//       steps{
//         // script {
//         //   dockerImage = docker.build dockerimagename
//         // }
//         echo 'build image the application...'
//       }
//     }

//     stage('Pushing Image') {
//       environment {
//                registryCredential = 'dockerhub-credentials'
//            }
//       steps{
//         // script {
//         //   docker.withRegistry( 'https://registry.hub.docker.com', registryCredential ) {
//         //     dockerImage.push("latest")
//         //   }
//         // }
//         echo 'pushing image the application...'
//       }
//     }

//     stage('Deploying React.js container to Kubernetes') {
//       steps {
//         // script {
//         //   kubernetesDeploy(configs: "deployment.yaml", "service.yaml")
//         // }
//         echo 'deploying the application...'
//       }
//     }

//   }

// }

pipeline {

    agent {
        docker {
            image 'node'
            args '-u root'
        }
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'npm test'
            }
        }
    }
}
