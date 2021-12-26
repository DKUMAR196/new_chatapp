pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                rsync -av -e "ssh -o StrictHostKeyChecking=no -i /var/lib/jenkins/New01key.pem" /var/lib/jenkins/workspace/NewOne/    ubuntu@10.0.2.96:/home/ubuntu/new_chatapp
            }
        }
        stage('Deploy') {
            steps {
                ssh -i /var/lib/jenkins/New01key.pem ubuntu@10.0.2.96 sudo systemctl restart gunicorn
            }
        }
    }
}
