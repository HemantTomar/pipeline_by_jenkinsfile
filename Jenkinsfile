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
                        deploy contextPath: null, **/*.html: 'http://18.191.61.124:9090/'
                  }
            }
            stage('Deploy Production') {
                  steps {
                        echo "Deploying in Production Area"
                  }
            }
      }
}
