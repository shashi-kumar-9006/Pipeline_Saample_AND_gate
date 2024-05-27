// Declarative Pipeline
pipeline {
   agent any
   environment {
       PATH = "C:\\Program Files\\MATLAB\\R2024a\\bin;${PATH}"   // Windows agent 
   }
    stages {
        stage('Run MATLAB Command') {
            steps {
               runMATLABCommand(command: 'disp("Hello World!")')
            }       
        }                
    } 
}
