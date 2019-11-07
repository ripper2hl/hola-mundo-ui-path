#!groovy
node("windows-slave") {
    def allJob = env.JOB_NAME.tokenize('/') as String[];
    def projectName = allJob[0];
    def buildPath = "${env.WORKSPACE}\\jobs\\${projectName}\\${BRANCH_NAME}\\builds\\${env.BUILD_NUMBER}";
    def buildPathArchive = "jobs\\${projectName}\\${BRANCH_NAME}\\builds\\${env.BUILD_NUMBER}";
    stage ('obtener fuentes'){
            echo 'Descargando código de SCM';
            cleanWs();
            checkout scm;
    }

    stage ('construccion'){
      bat label: '', script: "mkdir -p ${buildPath}";
      bat label: '', script: "C:\\Users\\vagrant\\AppData\\Local\\UiPath\\app-19.9.2\\UiRobot.exe -pack ${env.WORKSPACE}\\project.json -o ${buildPath}";
    }

    stage ('archivar'){
      step([$class: 'ArtifactArchiver', artifacts: "${buildPathArchive}\\*.nupkg", fingerprint: true]);
    }

 }
