#!groovy
node("windows-slave") {

    stage ('obtener fuentes'){
            echo 'Descargando código de SCM';
            cleanWs();
            checkout scm;
    }

    stage ('construccion'){
      bat label: '', script: "C:\\Users\\vagrant\\AppData\\Local\\UiPath\\app-19.9.2\\UiRobot.exe -pack ${env.WORKSPACE}\\project.json -o C:\\jenkins\\jobs\\${env.JOB_NAME}\\builds\\${env.BUILD_NUMBER}";
    }

    stage ('archivar'){
      def allJob = env.JOB_NAME.tokenize('/') as String[];
      def projectName = allJob[1];
      bat label: '', script: "dir  C:\\jenkins\\jobs\\${projectName}\\${BRANCH_NAME}\\builds\\${env.BUILD_NUMBER}";
    }

 }
