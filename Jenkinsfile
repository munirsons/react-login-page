pipeline {
    agent any

    stages {
         stage('Code Cloned') {
            steps {
                echo 'Hello shaheer'
                echo 'In this step we cloned code from github.com'
                git url: "https://github.com/munirsons/react-login-page.git", branch:"main"
                echo "code clonded from git hub successfully"
            }
        }
         stage('Code Build') {
            steps {
                echo 'In this step we build code to image through Docker'
                sh    "docker build -t react-page:latest ."
                echo "image build from git hub repositry successfully"
            }
        }
         stage('Code deployed') {
            steps {
                echo 'In this step code image is run through docker and deployed on the server by using docker container'
	            	sh   "docker run -d -p 8000:3000 react-page:latest"
                
            }
        }
    }
}
