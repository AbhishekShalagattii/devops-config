�
� ✅ FINAL WORKING STEPS: S3 
STATIC WEBSITE (GUARANTEED) 
� STEP 1: CREATE S3 BUCKET 
 Go to AWS → S3  
 Click Create bucket  
Fill: 
 Bucket name → my-static-site-123 (unique ⚠️)  
 Region → any  
�
� Click Create bucket 
� STEP 2: DISABLE BLOCK PUBLIC 
ACCESS 
�
� Open your bucket 
�
� Go to Permissions tab 
Click: 
�
� Edit (Block public access) 
� Uncheck: 
Block all public access ❌ 
✔ Tick “I acknowledge…” 
✔ Click Save changes 
� STEP 3: ENABLE STATIC WEBSITE 
HOSTING 
�
� Go to Properties tab 
Scroll to: 
�
� Static website hosting 
Click Edit 
✔ Enable 
✔ Index document: 
index.html 
�
� Save 
� STEP 4: CREATE WEBSITE FILE 
On your PC create: 
�
� index.html 
<!DOCTYPE html> 
<html> 
<head> 
<title>S3 Website</title> 
</head> 
<body> 
<h1>Hello from S3 Website 🚀</h1> 
</body> 
</html> 
� STEP 5: UPLOAD FILE 
�
� Go to Objects tab 
Click: 
�
� Upload → Add index.html → Upload 
� STEP 6: ADD BUCKET POLICY 
(MAIN STEP 🔥) 
�
� Go to Permissions tab 
Scroll → Bucket Policy → Edit 
�
� Paste THIS (VERY IMPORTANT) 
{ 
} 
"Version": "2012-10-17", 
"Statement": [ 
{ 
"Sid": "PublicRead", 
"Effect": "Allow", 
"Principal": "*", 
"Action": "s3:GetObject", 
"Resource": "arn:aws:s3:::my-static-site-123/*" 
} 
] 
� IMPORTANT 
�
� Replace: 
my-static-site-123 
with your actual bucket name 
�
� Click Save changes 
� STEP 7: OPEN WEBSITE URL 
�
� Go to Properties → Static website hosting 
Copy this URL: 
http://my-static-site-123.s3-website-<region>.amazonaws.com 
�
� STEP 8: OPEN IN BROWSER 
Paste URL in Chrome 
�
� FINAL OUTPUT 
Hello from S3 Website 🚀 
