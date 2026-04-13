�
� ✅ EXPERIMENT: Deploy Java App 
using Docker on AWS EC2 (FINAL 
CORRECT FLOW) 
� 🌐 PHASE 1: AWS EC2 SETUP 
1�⃣ Create EC2 Instance 
 Go to AWS Console → EC2  
 Click Launch Instance  
 Name: docker-java-server  
 OS: Ubuntu (Free Tier)  
 Instance type: t2.micro  
2�⃣ Create Key Pair 
 Name: docker-key.pem  
 Download it  
 Save in: Downloads  
3�⃣ Launch Instance 
 Allow SSH (port 22)  
 Click Launch  
�
� PHASE 2: CONNECT TO EC2 
Open CMD: 
ssh -i C:\Users\91935\Downloads\docker-key.pem ubuntu@<EC2-PUBLIC-IP> 
✔ You are now inside EC2 terminal 
�
� PHASE 3: INSTALL DOCKER ON EC2 
Run: 
sudo apt update -y 
sudo apt install docker.io -y 
sudo systemctl start docker 
sudo systemctl enable docker 
docker --version 
�
� PHASE 4: PREPARE JAVA PROJECT 
(LOCAL PC) 
Create folder: 
Docker_SET01/ 
Inside it: 
�
� Main.java 
public class Main { 
public static void main(String[] args) { 
System.out.println("Hello from Dockerized Java App 🚀"); 
} 
} 
�
� Dockerfile 
FROM eclipse-temurin:17-jdk 
WORKDIR /app 
COPY . . 
RUN javac Main.java 
CMD ["java", "Main"] 
�
� PHASE 5: SEND FILES TO EC2 (SCP) 
Go to project folder: 
cd C:\Users\91935\Desktop\Docker_SET01 
Then run: 
scp -i C:\Users\91935\Downloads\docker-key.pem Main.java Dockerfile 
ubuntu@<EC2-PUBLIC-IP>:~ 
✔ Files are now inside EC2 
�
� PHASE 6: VERIFY IN EC2 
Inside EC2: 
ls 
You should see: 
Main.java 
Dockerfile 
�
� PHASE 7: BUILD DOCKER IMAGE 
docker build -t java-app . 
✔ Docker: 
 pulls Java image  
 compiles code  
 creates image  
▶� PHASE 8: RUN CONTAINER 
docker run java-app 
�
� OUTPUT 
Hello from Dockerized Java App 🚀 
�
� PHASE 9: WHAT YOU WRITE IN 
RECORD (IMPORTANT FOR MARKS) 
�
� Steps (Write this) 
1. Created EC2 instance on AWS  
2. Connected using SSH  
3. Installed Docker on EC2  
4. Created Java application  
5. Created Dockerfile  
6. Transferred files using SCP  
7. Built Docker image  
8. Ran Docker container  
9. Verified output  
� DEVOPS FLOW DIAGRAM (WRITE 
IN EXAM) 
Developer PC → SCP → EC2 Instance → Docker Build → Docker Run → Output 
�
� WHY THIS IS FULL MARKS READY 
✔ Real cloud deployment 
✔ Docker containerization 
✔ Working Java app 
✔ Proper DevOps pipeline 
✔ Screenshot ready 
� BONUS TIP (VERY IMPORTANT FOR 
VIVA) 
If examiner asks: 
�
� Why Docker? 
Say: 
“Docker ensures application runs consistently across all environments without dependency 
issues.” 
