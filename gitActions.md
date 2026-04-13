DevOps Practical Experiment 
Title 
Implementation of CI/CD Pipeline using GitHub Actions 
1️⃣ Lab Program / Experiment Write-up 
(10 Marks) 
Aim 
To implement a Continuous Integration and Continuous Deployment (CI/CD) pipeline 
using GitHub Actions for automatically building and running a Java application whenever 
code is pushed to the repository. 
Objective 
• To understand the DevOps workflow 
• To automate build and testing process 
• To implement CI/CD using GitHub Actions 
• To integrate source code repository with automation pipeline 
Tools Required 
• Git 
• GitHub 
• GitHub Actions 
• Java Development Kit 
• Visual Studio Code 
Theory 
DevOps 
DevOps is a combination of Development and Operations practices that automates and 
integrates the processes between software development and IT teams. 
Continuous Integration (CI) 
Continuous Integration is a development practice where developers frequently integrate code 
into a shared repository. Each integration triggers an automated build and test process. 
Continuous Deployment (CD) 
Continuous Deployment ensures that after successful testing, the application is automatically 
deployed. 
GitHub Actions 
GitHub Actions is a CI/CD platform that allows developers to automate workflows such as 
build, test, and deployment directly from the repository. 
Workflows are defined using YAML configuration files placed inside: 
.github/workflows/ 
2️⃣ Tool Setup & Configuration / System 
Design (20 Marks) 
Step 1: Install Git 
Download and install Git 
Website 
https://git-scm.com 
Verify installation: 
git --version 
Step 2: Install Java 
Install Java Development Kit 
Verify installation: 
java -version 
javac -version 
Step 3: Create GitHub Account 
Go to: 
https://github.com 
Create an account in GitHub 
Step 4: Create a Repository 
1. Login to GitHub  
2. Click New Repository  
Repository Name: 
devops-cicd-demo 
Select: 
✔ Public 
✔ Add README 
Click Create Repository 
Step 5: Clone Repository 
Open terminal and run: 
git clone https://github.com/username/devops-cicd-demo.git 
Go inside project: 
cd devops-cicd-demo 
System Design (Draw this diagram in 
record) 
Developer 
| 
| git push 
v 
GitHub Repository 
| 
v 
GitHub Actions Workflow 
| 
v 
Build Stage 
| 
Compile Code 
| 
Run Program 
| 
v 
Output Logs 
3️⃣ Implementation of DevOps Workflow 
(20 Marks) 
Step 6: Create Java Program 
Create file: 
HelloWorld.java 
Program: 
public class HelloWorld { 
public static void main(String[] args) { 
System.out.println("Hello DevOps CI/CD using GitHub Actions"); 
} 
} 
Step 7: Test Program Locally 
Compile: 
javac HelloWorld.java 
Run: 
java HelloWorld 
Output: 
Hello DevOps CI/CD using GitHub Actions 
Step 8: Create Workflow Folder 
Inside repository create folder: 
.github/workflows 
Create file: 
ci.yml 
Final structure: 
devops-cicd-demo 
│ 
├── HelloWorld.java 
│ 
└── .github 
└── workflows 
└── ci.yml 
Step 9: Write GitHub Actions Pipeline 
Add this code in ci.yml 
name: Java CI Pipeline 
on: 
push: 
branches: - main 
jobs: 
build: 
runs-on: ubuntu-latest 
steps: - name: Checkout Code 
uses: actions/checkout@v3 - name: Setup Java 
uses: actions/setup-java@v3 
with: 
distribution: 'temurin' 
java-version: '17' - name: Compile Java Program 
run: javac HelloWorld.java - name: Run Java Program 
run: java HelloWorld 
Step 10: Push Code to GitHub 
Add files: 
git add . 
Commit: 
git commit -m "Added GitHub Actions CI pipeline" 
Push: 
git push origin main 
Step 11: Pipeline Execution 
After pushing code, **GitHub Actions automatically triggers the workflow. 
Go to: 
Repository → Actions 
You will see: 
Java CI Pipeline Running 
GitHub performs: 
✔ Checkout code 
✔ Setup Java 
✔ Compile program 
✔ Execute program 
Step 12: Verify Output 
Inside workflow logs you will see: 
Hello DevOps CI/CD using GitHub Actions 
This confirms successful CI/CD pipeline execution. 
Result 
The CI/CD pipeline using GitHub Actions was successfully implemented. The workflow 
automatically builds and executes the Java application whenever code is pushed to the 
repository. 
Advantages 
• Automated build and testing 
• Faster development cycle 
• Early detection of errors 
• Improved software quality 
Conclusion 
GitHub Actions provides an efficient CI/CD platform that automates software build and 
deployment workflows directly within GitHub repositories, improving productivity and 
development efficiency. 
