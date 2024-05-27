// Declarative Pipeline
pipeline {
   agent any
   environment {
       PATH = "C:\\Program Files\\MATLAB\\R2023b\\bin;${PATH}"   // Windows agent 
   }
    stages {
        stage('Run MATLAB Command') {
            steps {
               runMATLABCommand(command: 'disp("Hello World!")')
            }       
        }
       stage('Check Model Simulation') {
            steps {
                script {
                    def modelSimulated = runMATLABCommand(command: 'simulated = bdIsLoaded("and_gate_model.slx"); disp(simulated);', returnStdout: true).trim()
                    if (modelSimulated == 'true') {
                        echo 'The "and_gate_model.slx" model is being simulated.'
                    } else {
                        echo 'The "and_gate_model.slx" model is not being simulated.'
                    }
                }
            }
        }
       stage('Run MATLAB Tests') {
            steps {
                runMATLABTests(testResultsJUnit: 'test-results/results.xml',
                               codeCoverageCobertura: 'code-coverage/coverage.xml', 
                                 testResultsPDF: 'test-results/testreport.pdf')
            }       
        }  
    }
   } 

