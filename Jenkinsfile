#!groovy
node("windows-slave") {
    def allJob = env.JOB_NAME.tokenize('/') as String[];
    def projectName = allJob[0];
    stage ('obtener fuentes'){
            echo 'Descargando código de SCM';
            cleanWs();
            checkout scm;
    }

    stage ('construccion'){
      bat label: '', script: "mkdir -p C:\\jenkins\\jobs\\${projectName}\\${BRANCH_NAME}\\builds\\${env.BUILD_NUMBER}";
      bat label: '', script: "C:\\Users\\vagrant\\AppData\\Local\\UiPath\\app-19.9.2\\UiRobot.exe -pack ${env.WORKSPACE}\\project.json -o C:\\jenkins\\jobs\\${projectName}\\${BRANCH_NAME}\\builds\\${env.BUILD_NUMBER}";
    }

    stage ('archivar'){
      bat label: '', script: "dir  C:\\jenkins\\jobs\\${projectName}\\${BRANCH_NAME}\\builds\\${env.BUILD_NUMBER}";
    }

 }
