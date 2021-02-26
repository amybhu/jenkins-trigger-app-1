node {

    stage('Start'){
        checkout scm
    }
    stage('Docker Image Build & Push'){
        docker.withRegistry('https://registry.hub.docker.com', 'dockeHub') {

            def customImage = docker.build("aswinrprasad/jenkins-trigger-web:${env.BUILD_ID}")

            /* Push the container to the custom Registry */
            customImage.push()
        }
    }
    stage('Complete'){

        sh "echo 'Build Successful'"
    }
}