pipline{
        agent any
                  stages{
                          stage('Build image') {app = docker.build("ikhan206/coursework2")}
                          stage('Push image') {docker.withRegistry('https://hub.docker.com', 'docker-hub-credentials')
                                        app.push("latest")}
                          stage('Sonarqube'){
                                  enviroment{ scanner home = tool 'Sonarqube'}
                                          Steps{
                                                  withSonarQubeEnv('Sonarqube'){sh "${scannerHome}/bin/sonar-scanner"}

                                                  timeout(time: 10, unit: 'MINUTES') {
                                                  waitForQualityGate abortPipeline: true
                                               }
                                            }
                        }
       }

