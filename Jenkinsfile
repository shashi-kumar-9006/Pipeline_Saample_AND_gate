// // // Declarative Pipeline
// // pipeline {
// //    agent any
// //    environment {
// //        PATH = "C:\\Program Files\\MATLAB\\R2023b\\bin;${PATH}"   // Windows agent
// //    }
// //     stages {
// //         stage('Simulate Model') {
// //     steps {
// //         script {
// //             try {
// //                 bat """
// //                     "${PATH}" -nodisplay -nosplash -r "cd('${WORKSPACE}'); load_system('and_gate_model'); sim('and_gate_model');"
// //                     echo Model simulation successful
// //                 """
// //             } catch (exc) {
// //                 echo "Model simulation failed: ${exc}"
// //             }
// //         }
// //     }
// // }
// //     }
// // }

// pipeline {
//     agent any
 
//     stages {
//         stage('Checkout') {
//             steps {
//                 checkout scm
//             }
//         }
 
//         stage('Model Simulation') {
//             steps {
//                 script {
//                     try {
//                         // Run MATLAB model simulation
//                         bat """
//                             @echo off
//                             cd /d "C:\\Program Files\\MATLAB\\R2023b"
//                             "C:\\Program Files\\MATLAB\\R2023b\\bin\\matlab.exe" -nodisplay -nosplash -r "run('and_gate_model.slx'); exit;"
//                         """
//                     } catch (exc) {
//                         currentBuild.result = 'FAILURE'
//                         echo 'MATLAB model simulation failed: ' + exc.toString()
//                     }
//                 }
//             }
//         }
//     }
 
//     post {
//         failure {
//             echo 'Pipeline failed'
//         }
//     }
// }


pipeline {
    agent any

    environment {
        MATLAB_ROOT = "/path/to/MATLAB/R2023b"  // Replace with the actual path to your MATLAB installation
        GIT_REPO_URL = "https://github.com/shashi-kumar-9006/harsh-test/"  // Replace with the URL of your GitHub repository
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: "${GIT_REPO_URL}"  // Replace 'main' with your branch name
            }
        }

        stage('Simulate Model') {
            steps {
                script {
                    try {
                        bat """
                            "${MATLAB_ROOT}\\bin\\matlab" -nodisplay -nosplash -r "cd('${env.WORKSPACE}'); load_system('and_gate_model'); sim('and_gate_model');"
                            echo Model simulation successful
                        """
                    } catch (exc) {
                        echo "Model simulation failed: ${exc}"
                    }
                }
            }
        }

        // Other stages...
    }
}
