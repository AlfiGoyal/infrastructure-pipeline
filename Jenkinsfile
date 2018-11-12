properties([pipelineTriggers([githubPush()])])
node('linux') {
    git url: 'https://github.com/AlfiGoyal/infrastructure-pipeline.git', branch: 'master'
    stage ("GetInstances") {
        sh "aws ec2 describe-instances --region us-east-1"
    }
    stage ("CreateInstance") {
        sh "aws ec2 run-instances --image-id ami-013be31976ca2c322 --count 1 --instance-type t2.micro --key-name Assignment2key --security-group-ids sg-dfaaf893 --subnet-id subnet-f831b69f --region us-east-1"
    }
}
