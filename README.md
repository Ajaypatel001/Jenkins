#---------------git install ---------------

sudo yum install git -y


#-------java dependency for jenkins------------

sudo yum install java-17-amazon-corretto.x86_64


#------------jenkins install-------------
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
sudo yum install jenkins -y
sudo systemctl enable jenkins
sudo systemctl start jenkins


# ------------------install terraform ------------------

sudo yum install -y yum-utils
sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/AmazonLinux/hashicorp.repo
sudo yum -y install terraform


{
  "title": "Jenkins + Terraform on AWS (CI/CD Automation)",
  "overview": {
    "what_is_jenkins": "Jenkins is an open-source CI/CD automation tool used to automate build, test, and deployment processes.",
    "project_description": "This project explains how to set up Jenkins and Terraform on an AWS EC2 (Amazon Linux) server for CI/CD and Infrastructure Automation."
  },
  "tools_used": [
    "Jenkins - CI/CD Automation",
    "Git - Source Code Management",
    "Java - Jenkins Dependency",
    "Terraform - Infrastructure as Code",
    "AWS EC2 - Cloud Server"
  ],
  "setup": {
    "platform": "AWS EC2 (Amazon Linux)",
    "steps": [
      {
        "step": "Install Git",
        "commands": [
          "sudo yum install git -y"
        ]
      },
      {
        "step": "Install Java (Required for Jenkins)",
        "commands": [
          "sudo yum install java-17-amazon-corretto.x86_64 -y"
        ]
      },
      {
        "step": "Install Jenkins",
        "commands": [
          "sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo",
          "sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key",
          "sudo yum install jenkins -y",
          "sudo systemctl enable jenkins",
          "sudo systemctl start jenkins"
        ]
      },
      {
        "step": "Access Jenkins",
        "details": {
          "url": "http://<EC2-Public-IP>:8080",
          "admin_password_command": "sudo cat /var/lib/jenkins/secrets/initialAdminPassword"
        }
      },
      {
        "step": "Install Terraform",
        "commands": [
          "sudo yum install -y yum-utils",
          "sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/AmazonLinux/hashicorp.repo",
          "sudo yum install terraform -y"
        ]
      }
    ]
  },
  "workflow": "Developer → GitHub → Jenkins → Terraform → AWS Infrastructure",
  "verification_commands": [
    "git --version",
    "java -version",
    "terraform --version"
  ],
  "learning_outcomes": [
    "Understanding what Jenkins is and why it is used",
    "Setting up Jenkins on AWS EC2",
    "Installing Git, Java, Jenkins, and Terraform",
    "Using Jenkins with Terraform for automation",
    "Basic CI/CD workflow knowledge"
  ],
  "author": "Ajay Patel"
}
