pipeline {
    agent any

    tools {
        jdk 'jdk21'              // Must match the name you gave in step 1
        maven 'Maven 3.9.2'      // Or your Maven version name
    }

    stages {
        stage('Welcome Stage') {
            steps {
                echo "Welcome to Pipeline"
            }
        }

        stage('Maven Build') {
            steps {
                bat 'mvn clean install' // Includes test by default
            }
        }

        stage('Run Tests') {
            steps {
                echo "Running Unit Tests"
                // Optional: You can explicitly run 'mvn test' here
                bat 'mvn test'
            }
        }

        stage('Publish Test Results') {
            steps {
                junit 'target/surefire-reports/*.xml' // Standard JUnit report location for Maven
            }
        }

        stage('Build Success') {
            steps {
                echo "Build Successful"
            }
        }
    }
}


// pipeline {
//     agent any
//     tools {
//         maven 'MAVEN_HOME'
//     }
//     stages {
//         stage('Welcome Stage') {
//             steps {
//                 echo "Welcome to Pipeline"
//             }
//         }
//         stage('Maven Build') {
//             steps {
//                 bat 'mvn install'
//             }
//         }
//         stage('Build Success') {
//             steps {
//                 echo "Build Successful"
//             }
//         }
//     }
// }
