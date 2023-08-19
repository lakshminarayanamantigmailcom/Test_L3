pipeline {
    agent {label 'JDK'}
    parameters {
            choice(name: 'BRANCH', choices: ['master', 'main', 'lokesh'], description: 'Pick something')
            choice(name: 'BUILD',  choices: ['package', 'install', 'Test'], description: 'build')
    }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/spring-projects/spring-petclinic.git',
                branch: "${prams.BRANCH}"
            }
        }
        stage('build') {
            steps {
                sh "${prams.BUILD}"
            }
        }
    }
}