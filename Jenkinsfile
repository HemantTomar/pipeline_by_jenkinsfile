pipeline {
      agent any
      stages {
            stage('checkout from scm') {
                  steps {
                        echo 'Hi, this is Hemant Kumar from 3 Pillar Global'
                        git 'https://github.com/HemantTomar/pipeline_by_jenkinsfile.git'
                  }
            }
            stage('Build') {
                  steps {
                        echo 'Building Sample Simple Project'
                        archiveArtifacts '**/*.*'
                        
                  }
            }
            stage('Deploy') {
                  steps {
                        echo "Deploying in Staging Area"
                        copyArtifacts filter: '**/*.*', fingerprintArtifacts: true, projectName: 'pipe2'
                        sh 'sudo cp -r /var/lib/jenkins/workspace/pipe2 /opt/tomcat/tomcat_stag_9090/webapps/
                  }
            }
            stage('Deploy Production') {
                  steps {
                        echo "Deploying in Production Area"
                  }
            }
      }
}
