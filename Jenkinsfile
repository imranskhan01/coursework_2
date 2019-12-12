pipline{
        agent any
                  stages{
                          stage('One') {app = docker.build("ikhan206/coursework2")}
                          stage('Two') {docker.withRegistry('https://hub.docker.com', 'docker-hub-credentials')
                                        app.push("latest")}
                          stage('Three') {}
                        }
       }
