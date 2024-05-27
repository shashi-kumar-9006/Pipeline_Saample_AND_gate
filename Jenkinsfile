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
       stage('Run MATLAB Tests') {
            steps {
                runMATLABTests(testResultsJUnit: 'test-results/results.xml',
                               codeCoverageCobertura: 'code-coverage/coverage.xml',
            }       
        }  
    }
                               } 
}
