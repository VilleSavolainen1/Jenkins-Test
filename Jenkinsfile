pipeline {
    agent any

    stages {
        stage("foo") {
            steps {
                // all credential values are available for use but will be masked in console log
                sh 'echo "FOO is $FOO"'
                sh 'echo "FOO_USR is $FOO_USR"'
                sh 'echo "FOO_PSW is $FOO_PSW"'

                //Write to file
                dir("combined") {
                    sh 'echo $FOO > foo.txt'
                }
                sh 'echo $FOO_PSW > foo_psw.txt'
                sh 'echo $FOO_USR > foo_usr.txt'
                archive "**/*.txt"
            }
        }
    }
}