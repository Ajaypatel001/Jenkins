🚀 DevOps Tools Setup (Git, Jenkins, Terraform)
📌 Install Git
sudo yum install git -y
📌 Install Java (Jenkins Dependency)
sudo yum install java-17-amazon-corretto.x86_64 -y
java -version
📌 Install Jenkins
# Add repo
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo

# Import key
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key

# Install Jenkins
sudo yum install jenkins -y

# Enable & start
sudo systemctl enable jenkins
sudo systemctl start jenkins

# Check status
sudo systemctl status jenkins
📌 Install Terraform
sudo yum install -y yum-utils
sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/AmazonLinux/hashicorp.repo
sudo yum install terraform -y
terraform -version
✅ Summary

Git → Version control

Java → Required for Jenkins

Jenkins → CI/CD automation

Terraform → Infrastructure as Code
