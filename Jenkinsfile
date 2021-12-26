pipeline {
agent any
 stages {
  stage('Build') {
   steps {
    sh 'rsync -av -e "ssh -o StrictHostKeyChecking=no -i /var/lib/jenkins/New01key.pem" /var/lib/jenkins/workspace/Pipeline/    ubuntu@10.0.2.96:/home/ubuntu/new_chatapp'
   }
 }
 stage('Deploy') {
  steps {
   sh 'ssh -i /var/lib/jenkins/New01key.pem ubuntu@10.0.2.96 sudo systemctl restart gunicorn'
  }
 }
}
}
