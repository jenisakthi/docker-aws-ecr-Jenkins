# docker-aws-ecr-Jenkins

sudo wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
sudo yum upgrade -y 
# Add required dependencies for the jenkins package
sudo yum install java-11-openjdk -y
sudo yum install jenkins -y 
sudo systemctl daemon-reload


# docker installation ( on both machine)

 sudo yum install -y yum-utils
 sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo -y 
sudo yum install docker-ce docker-ce-cli containerd.io -y 
sudo systemctl start docker

# aws cli ( on both machine) 

curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 841646215071.dkr.ecr.us-east-1.amazonaws.com

# install git
yum install git -y


# reguired plugins
SSH Agent 
Version
1.24.1

# steps
## on jenkins
- install aws
- install docker
- install jenkins
- install git
- `aws configure` ( configure for ecr region) 
- docker login for aws container registery 
