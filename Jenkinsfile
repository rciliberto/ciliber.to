def projectVersion

def getGitBranchName() {
    def branch = scm.branches[0].name
    echo branch
}

def getGitMainRev() {
    def main = sh(returnStdout:true, script:'git rev-parse origin/main')
    echo main
}

def getGitDevelopRev() {
    def dev = sh(returnStdout:true, script:'git rev-parse origin/develop')
    echo dev
}

pipeline {
    agent any

    tools {
        maven 'Default'
    }

    stages {
        stage('Verify Develop not at Main') {
            when {
                expression {
                    getGitDevelopRev() != getGitMainRev() || getGitBranchName() == '*/main'
                }
            }
            stages {
                stage('Get Project Version') {
                    steps {
                        script {
                            projectVersion = sh(returnStdout:true, script:'mvn help:evaluate -Dexpression=jgitver.calculated_version -q -DforceStdout')
                            echo projectVersion
                        }
                    }
                }
                stage('Build Image') {
                    steps {
                        sh "docker build -t ciliberto/website:${projectVersion} ."
                    }
                }
                stage('Tag Image As Latest') {
                    steps {
                        script {
                            sh "docker tag ciliberto/website:${projectVersion} ciliberto/website:latest"

                            if (getGitBranchName() == '*/main') {
                                sh "docker tag ciliberto/website:${projectVersion} ciliberto/website:latest-stable"
                            }
                        }
                    }
                }
                stage('Push to Local Registry') {
                    steps {
                        script {
                            withCredentials([usernamePassword(credentialsId: 'docker-registry', passwordVariable: 'password', usernameVariable: 'username')]) {
                                sh "docker login docker.ciliber.to --username ${username} --password ${password}"
                                sh "docker tag ciliberto/website:${projectVersion} docker.ciliber.to/ciliberto/website:${projectVersion}"
                                sh "docker tag ciliberto/website:${projectVersion} docker.ciliber.to/ciliberto/website:latest"
                                sh "docker push docker.ciliber.to/ciliberto/website:${projectVersion}"
                                sh "docker push docker.ciliber.to/ciliberto/website:latest"

                                if (getGitBranchName() == '*/main') {
                                    sh "docker tag ciliberto/website:${projectVersion} docker.ciliber.to/ciliberto/website:latest-stable"
                                    sh "docker push docker.ciliber.to/ciliberto/website:latest-stable"
                                }
                            }
                        }
                    }
                }
                stage('Remove Local Tags') {
                    steps {
                        script {
                            sh "docker image rm ciliberto/website:latest"
                            sh "docker image rm ciliberto/website:${projectVersion}"
                            if (getGitBranchName() == '*/main') {
                                sh "docker image rm ciliberto/website:latest-stable"
                            }
                        }
                    }
                }
            }
        }
    }
    post {
        success {
            echo "Build suceeded: ciliberto/website:${projectVersion}"
        }
    }
}