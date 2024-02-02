pipeline {
    agent {
    node {
        label 'AGENT-1'
        
    }
    }
    environment{
        versionId = ""
    }

    // parameters {
    //     string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

    //     text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

    //     booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

    //     choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

    //     password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    // }
    // build
    stages {
        stage('Build version') {
            steps {
                script{
                    def packageJson = readJSON file: 'package.json'
                    versionId = packageJson.version
                    echo "application version is : $versionId"
                }
            }
        }
        stage('Build version') {
            steps {
                sh """
                    npm install 
                """
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        // stage('check params'){
        //     steps{
        //         sh """
        //             echo "Hello ${params.PERSON}"

        //             echo "Biography: ${params.BIOGRAPHY}"

        //             echo "Toggle: ${params.TOGGLE}"

        //             echo "Choice: ${params.CHOICE}"

        //             echo "Password: ${params.PASSWORD}"
        //         """
        //     }
    
        // }
    }
    // after build execution post is used check the status of execution 
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure { 
            echo 'The jenkins script is failed'
        }
        success { 
            echo 'The jenkins script is passed successfully'
        }
        
    }
}


