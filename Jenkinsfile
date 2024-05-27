// // Declarative Pipeline
// pipeline {
//    agent any
//    environment {
//        PATH = "C:\\Program Files\\MATLAB\\R2023b\\bin;${PATH}"   // Windows agent
//    }
//     stages {
//         stage('Simulate Model') {
//             steps {
//                 script {
//                     try {
//                         sh """
//                             ${PATH}/bin/matlab; load_system('and_gate_model'); sim('and_gate_model');"
//                             echo "Model simulation successful"
//                         """
//                     } catch (exc) {
//                         echo "Model simulation failed: ${exc}"
//                     }
//                 }
//             }
//         }
//     }
// }

pipeline {
    agent any

    environment {
        MATLAB_ROOT = 'C:\\Program Files\\MATLAB\\R2023b'
    }

    stages {
        stage('Simulate Model') {
            steps {
                script {
                    try {
                        bat """
                            call "${MATLAB_ROOT}\\bin\\matlab.bat" -nodesktop -nosplash -r "load_system('and_gate_model'); sim('and_gate_model'); exit;"
                            echo "Model simulation successful"
                        """
                    } catch (exc) {
                        echo "Model simulation failed: ${exc}"
                    }
                }
            }
        }
    }
}
