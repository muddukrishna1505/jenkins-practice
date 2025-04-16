pipeline {
    agent any
    parameters {
        string(name: 'PERSON', defaultValue: 'MRJenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages{
        stage("print parameters"){
            steps{
                echo "Person name is: ${params.PERSON}"
            }
        }
        
        stage('input') {
            input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
            }
            steps {
                echo "Hello, ${PERSON}, nice to meet you."
            }
        }
        
        stage("cloning"){
            steps{
                echo "welcome to Jenkins"
            }
        }
        
        stage("conditions"){
            when {
                 expression { return params.TOGGLE}  
                }
            steps{
                echo "this is for prod"
            }
        }

    }
}
