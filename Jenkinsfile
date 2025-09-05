pipeline {
    agent any
    parameters {
        choice(name: 'BUILD_TYPE', choices: ['development', 'production'], description: 'Select the build type')
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
