#!groovy

// for more information about TestRunner please visit https://github.com/saucelabs/pipeline-test-runner

@Library('TestRunner') _

def collectReports = COLLECT_JUNIT_ENABLED.is("true")

TestRunner {
    steps = {
        sh "./gradlew clean test -i"
        archiveArtifacts "screenshot.png"
    }
    dockerImage = "java:8"
    collectJunitReport = collectReports
    junitReportPath = "**/TEST-*.xml"
}
