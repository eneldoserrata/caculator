pipeline {
agent any
    stages {
        stage("Compile") {
            steps {
                sh "./gradlew compileJava"
            }
        }
        stage("Code coverage") {
            steps {
                sh "./gradlew jacocoTestReport"
                publishHTML (target: [
                    reportDir: "build/report/jacoco/test/html",
                    reportFiles: "index.html",
                    reportName: "Jacoco Report"
                ])
                sh "./gradlew jacocoTestCoverageVerification"
            }
        }
    }
}