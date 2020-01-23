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
                        archiveArtifacts '/var/lib/jenkins/workspace/pipe2/*.war'
                        
                  }
            }
            stage('Deploy') {
                  steps {
                        echo "Deploying in Staging Area"
                        copyArtifacts filter: '**/*.war', fingerprintArtifacts: true, projectName: 'pipe2'
                        deploy adapters: [tomcat9(credentialsId: '664ee0b6-405c-4fd9-926d-01a864a96c6b', path: '', url: 'http://18.191.61.124:9090/')], contextPath: '/', war: '**/*.war'
                  }
            }
            stage('Deploy Production') {
                  steps {
                        echo "Deploying in Production Area"
                  }
            }
      }
}
