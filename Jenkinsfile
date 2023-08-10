pipeline{
    agent{
        label 'master'
    }
    tools {
        maven 'Maven' 
    }
    stages{
        stage("test"){
            steps{
                //mvn test
                
                sh "mvn --version"
                echo "========executing A========"
            }    

        }
        stage("Build"){
            steps{
                //mvn package
                sh "mvn package"
                echo "========executing A========"
            }
            
        }
        stage("Deploy on the test server"){
            steps{
                //deploy on container ->plugin
                deploy adapters: [tomcat9(credentialsId: 'tomcatserverdetails', path: '', url: 'http://34.16.132.236:8080')], contextPath: '/app', war: '**/*.war'
                echo "========executing A========"
            }
            
        }
        stage("Deploy on the prod server"){
            steps{
                //deploy on container ->plugin
                deploy adapters: [tomcat9(credentialsId: 'tomcatserverdetails', path: '', url: 'http://34.16.158.166:8080')], contextPath: '/app', war: '**/*.war'
                echo "========executing A========"
            }
            
        }
        
    }
}
            
