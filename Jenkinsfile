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
                    // Step 1: Run and gate model simulation
                    try {
                        // Run simulation code here
                        bat 'matlab -r "run_simulation(\'and_gate_model.slx\')"'
                        // Custom try block comment
                        echo 'Simulation ran successfully.'
                    } catch (Exception e) {
                        // Custom catch block comment
                        echo 'Simulation failed.'
                    }
                }
            }
        }
    }
}

