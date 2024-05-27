// Declarative Pipeline
pipeline {
   agent any
   environment {
       PATH = "C:\\Program Files\\MATLAB\\R2023b\\bin;${PATH}"   // Windows agent
   }
    stages {
        stage('Simulate Model') {
            steps {
                script {
                    try {
                        sh """
                            ${MATLAB_ROOT}/bin/matlab -nodisplay -nosplash -r "cd('${WORKSPACE}'); load_system('and_gate_model'); sim('and_gate_model');"
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

