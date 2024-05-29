// Declarative Pipeline
pipeline {
   agent any
   environment {
       PATH = "C:\\Program Files\\MATLAB\\R2023b\\bin;${PATH}"   // Windows agent 
   }
    stages {
        stage('Run MATLAB Command1') {
            steps {
               runMATLABCommand(command: 'disp("Hello World!")')
            }       
        }
       stage('Run MATLAB Tests') {
            steps {
                runMATLABTests(testResultsJUnit: 'test-results/results.xml',
                               codeCoverageCobertura: 'code-coverage/coverage.xml', 
                                 testResultsPDF: 'test-results/testreport.pdf')
            }
        }
       stage('Run MATLAB Command2') {
            steps {
                runMATLABCommand(command: 'simulation_check')
            }       
        }
       stage('Run MATLAB Command3') {
            steps {
                runMATLABCommand(command: 'jmaab_check')
            }       
        }
       stage('Run MATLAB Command4') {
            steps {
                runMATLABCommand(command: 'code_generation')
            }       
        }
    }
   } 

