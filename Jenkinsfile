node {

    stage('Start'){
        checkout scm
    }
    stage('Docker Image Build & Push'){
        docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {

            def customImage = docker.build("aswinrprasad/jenkins-trigger-web")

            /* Push the container to the custom Registry */
            customImage.push()
        }
    }
    stage('Complete'){

        sh "echo 'Build Successful'"
    }
}