#!groovy
node("windows-slave") {

    stage ('obtener fuentes'){
            echo 'Descargando código de SCM';
            cleanWs();
            checkout scm;
    }

    stage ('construccion'){
      UiPathPack outputPath: '${JENKINS_HOME}\\jobs\\${JOB_NAME}\\builds\\${BUILD_NUMBER}', projectJsonPath: '${WORKSPACE}', version: AutoVersion()
    }

    stage ('archivar'){
      sh "ls ${env.JENKINS_HOME}\\jobs\\${env.JOB_NAME}\\builds\\${env.BUILD_NUMBER}";
    }

 }
