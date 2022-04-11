pipeline{
    agent{
        kubernetes{
            yamlFile "jenkins-pod.yaml"
        }
    }
    stages{
        stage('Build & Deploy'){
            stages{
                stage('maven'){
                    steps{
                        container('maven'){
                            sh'''
                            echo "Hello world"
                            mvnn -v
                            '''
                        }

                    }
                }     
            }
            post{
                failure{
                    echo "build failed for unknown reasons"
                }
            }
        }
    }
}