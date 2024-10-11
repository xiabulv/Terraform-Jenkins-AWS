1.Lunch the EC2 on aws

2.Install Jenkins
(1)Minimum hardware requirements:256 MB of RAM,1 GB of drive space (although 10 GB is a recommended minimum if running Jenkins as a Docker container)
(2)Long Term Support release(Use Ubuntu 22.04 as example)
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
(3)Install java:
sudo apt update
sudo apt install fontconfig openjdk-17-jre
java -version
Reference Link : https://www.jenkins.io/doc/book/installing/linux/

3.Install Terraform 
(1)Ensure that your system is up to date and you have installed the gnupg, software-properties-common, and curl packages installed.
sudo apt-get update && sudo apt-get install -y gnupg software-properties-common
(2)Install the HashiCorp GPG key.
wget -O- https://apt.releases.hashicorp.com/gpg | \
gpg --dearmor | \
sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg > /dev/null
(3)Verify the key's fingerprint.
gpg --no-default-keyring \
--keyring /usr/share/keyrings/hashicorp-archive-keyring.gpg \
--fingerprint
(4)Add the official HashiCorp repository to your system.
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
sudo tee /etc/apt/sources.list.d/hashicorp.list
(5)Download the package information from HashiCorp.
sudo apt update
(6)Install Terraform from the new repository.
sudo apt-get install terraform
Reference Link : https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli

4.Install AWS Cli 
(1)Install AWS CLI v2 zip:
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
(2)Unzip file
unzip awscliv2.zip
(3)Install aws cli
sudo ./aws/install
(4)Verify installation
sudo ./aws/install
(5)Configure aws
aws configure

5.Login the Jenkins

