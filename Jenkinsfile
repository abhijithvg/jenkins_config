pipeline {
    agent any

    stages {
        stage ('Get Project') {
            steps {
                git url: 'https://github.com/abhijithvg/jenkins_config.git'
            }
        }
        stage ('Load Env') {
            steps {
                echo "WORKSPACE = ${workspace}"
                sh 'export PATH=/bin/bash:$PATH'
                script {
                  mypath = "${workspace}/config.properties"
                }
                loadProperties(mypath)
            }
        }
        stage ('Print Env') {
            steps {
                sh 'env'
            }
        }
    }
}
def loadProperties(path) {
    properties = new Properties()
    File propertiesFile = new File(path)
    properties.load(propertiesFile.newDataInputStream())
    Set<Object> keys = properties.keySet();
    for(Object k:keys){
    String key = (String)k;
    String value =(String) properties.getProperty(key)
    env."${key}" = "${value}"
    }
}
