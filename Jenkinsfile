// Declarative Pipeline
pipeline {
   agent any
   environment {
       PATH = "C:\\Program Files\\MATLAB\\R2023b\\bin;${PATH}"   // Windows agent
   }
    stage('Simulate Model') {
    steps {
        script {
            try {
                bat """
                    "${PATH}" -nodisplay -nosplash -r "cd('${WORKSPACE}'); load_system('and_gate_model'); sim('and_gate_model');"
                    echo Model simulation successful
                """
            } catch (exc) {
                echo "Model simulation failed: ${exc}"
            }
        }
    }
}
}

