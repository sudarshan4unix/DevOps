pipeline {
        agent any
                stages {
                        stage('One') {
                                steps {
                                        echo 'Hi, Sudarshan here!'
                                    }
                                }
                        stage('Two') {
                                steps {
                                        input('Do you want to proceed')
                                    }
                                }
                        stage('Three') {
                                        when {
                                                not {
                                                        branch "master"
                                                    }
                                            }
                                steps {
                                        echo 'Hello Sudarshan'
                                    }
                                }
                        stage('Four') {
                                        parallel {
                                            stage('Unit Test') {
                                                steps {
                                                    echo 'Running the unit test..'
                                                }
                                            }
                                            stage('Intgegration Test') {
                                                agent {
                                                    docker {
                                                        reuseNode false
                                                        image 'ubuntu'
                                                        }
                                                    }
                                                    steps {
                                                        echo "Running Integration test"
                                                    }
                                            }
                                                      
                                    }
                                
}
}
}
