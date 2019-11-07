#!groovy
node {

    stage ('obtener fuentes'){
            echo 'Descargando código de SCM';
            cleanWs();
            checkout scm;
    }

    stage ('construccion'){
      UiPathPack (outputPath: "${env.JENKINS_HOME}\\jobs\\${env.JOB_NAME}\\builds\\${env.BUILD_NUMBER}", projectJsonPath: "${env.WORKSPACE}", version: [$class: 'ManualEntry', text: "${MAJOR}.${MINOR}.${env.BUILD_NUMBER}"])
    }

 }
