// Declarative Pipeline
pipeline {
   agent any
   environment {
       PATH = "C:\\Program Files\\MATLAB\\R2024a\\bin;${PATH}"   // Windows agent
    // PATH = "/usr/local/MATLAB/R2024a/bin:${PATH}"   // Linux agent
    // PATH = "/Applications/MATLAB_R2024a.app/bin:${PATH}"   // macOS agent    
   }
    stages {
        stage('Run MATLAB Command') {
            steps {
               runMATLABCommand(command: 'disp("Hello World!")')
            }       
        }                
    } 
}
