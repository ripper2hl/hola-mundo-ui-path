#!groovy
node("windows-slave") {

    stage ('obtener fuentes'){
            echo 'Descargando código de SCM';
            cleanWs();
            checkout scm;
    }

    stage ('construccion'){
      UiPathPack (outputPath: "${env.JENKINS_HOME}\\jobs\\${env.JOB_NAME}\\builds\\${env.BUILD_NUMBER}", projectJsonPath: "${env.WORKSPACE}", version: [$class: 'ManualEntry', text: "1.0.${env.BUILD_NUMBER}"])
    }

    stage ('archivar'){
      sh "ls ${env.JENKINS_HOME}\\jobs\\${env.JOB_NAME}\\builds\\${env.BUILD_NUMBER}";
    }

 }
