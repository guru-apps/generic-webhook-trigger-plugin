pipeline { //1
    agent { //2
        kubernetes { //3
            defaultContainer 'jnlp'
            yaml """
apiVersion: v1
kind: Pod
metadata:
  labels:
    some-label: some-label-value
spec:
  containers:
  - name: maven
    image: maven:alpine
    command:
    - cat
    tty: true
"""
        } //3
    } // 2
    stages { //1

        stage('Run maven') { //2
            steps {
                container('maven') { //3

                        sh "mvn -e clean verify -DskipTests"
                 } //3
            } //2
        } //1

    }
} //1
