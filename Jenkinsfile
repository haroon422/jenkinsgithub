pipeline
{
    agent any
    stages{
        stage("sc-checkin")
        {
            steps
            {
                git branch: 'main', url: 'https://github.com/haroon422/jenkinsgithub.git'
                mail bcc: '', body: 'sc from project https://github.com/haroon422/jenkinsgithub.git is succesfully cloned', cc: '', from: '', replyTo: '', subject: 'sc succesfully cloned', to: 'haroonmd127@gmail.com'
            }
        }
        stage("build")
        {
            steps
            {
                sh 'mvn script'
            }
        }
        stage("deploytotest")
        {
            steps
            {
                 mail bcc: '', body: 'please approve', cc: '', from: '', replyTo: '', subject: 'waiting for approval from mounika', to: 'jaya@gmail.com'
                input message: 'waiting for approval from mounika', submitter: 'mounika'
               
            }
        }
    }
        post
        {
            success
            {
                mail bcc: '', body: 'project finished', cc: '', from: '', replyTo: '', subject: 'project success ', to: 'haroonmd127@gmail.com'
            }
            failure
            {
                mail bcc: '', body: 'project failed', cc: '', from: '', replyTo: '', subject: 'project failed', to: 'haroonmd127@gmail.com'
            }
        }    
}
