pipeline {
    agent {label 'JDK'}
    parameters {
            choice(name: 'BRANCH', choices: ['master', 'main', 'lokesh'], description: 'Pick something')
            string(name: 'BUILD', defaultValue: 'package', description: 'build')
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