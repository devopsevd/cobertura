node{

    checkout scm
    def mvnHome
    dir('BuildQuality'){
        stage('Preparation'){
                        
            git 'https://github.com/devopsevd/simple-spring.git'
            mvnHome = tool 'Maven'
        }

        stage('Build') {
            // Run the maven build
            if (isUnix()) {
                sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean cobertura:cobertura -Dcobertura.report.format=xml"
            } else {
                //bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
            }
        }
        


        stage('Unit Test Results') {
            //junit '**/target/surefire-reports/TEST-*.xml'
            //archive 'target/*.jar'
            //step([$class: 'CoberturaPublisher', autoUpdateHealth: false, autoUpdateStability: false, coberturaReportFile: '**/target/site/cobertura/coverage.xml', failUnhealthy: false, failUnstable: false, maxNumberOfBuilds: 0, onlyStable: false, sourceEncoding: 'ASCII', zoomCoverageChart: false])
        }

    }
}
