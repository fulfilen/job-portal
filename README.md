# Job-Portal

The online job portal application allows job seekers and recruiters to connect.The application provides the ability for job seekers to create their accounts, upload their profile and resume, search for jobs, apply for jobs, view different job openings. The application provides the ability for companies to create their accounts, search candidates, create job postings, and view candidates applications.

# View Tutorials (Series Completed)

Job Portal (PHP) - Part 1 - Introduction & User Login/Registration - https://youtu.be/3VGxEEpWEaw

Job Portal (PHP) - Part 2 - User Dashboard & Profile Updating - https://youtu.be/VkKXaqFafRA

Job Portal (PHP) - Part-3 - Company Login/Registration & Creating Job Posts - https://youtu.be/OiapxMhgH_I

Job Portal (PHP) - Part 4 - View/Edit/Delete Job Posts - https://youtu.be/E1F-snEgpPs

Job Portal (PHP) - Part 5 - Showing Random Job Post On Homepage & User Applying To Job - https://youtu.be/3qmjqLx3o6o

Job Portal (PHP) - Part 6 - Code Refactor & Bug Fix - https://youtu.be/YVv_JCcVb7s

Job Portal (PHP) - Part 7 - Job Search Page With Advanced Searching Options  - https://youtu.be/wgNd-HgxqJg

Job Portal (PHP) - Part 8 - Generating Resume By Filling Form Using Custom Resume Templates - https://youtu.be/Wndjgmk1SyM

Job Portal (PHP) - Part 9 - Uploading Resume & Company View/Reject User Application - https://youtu.be/SMjiO0UwAoA

Job Portal (PHP) - Part 10 - Admin Panel - https://youtu.be/UdLpBUR2lCs

Job Portal (PHP) - Part 11 - Admin Verifying Company & User Email Verification - https://youtu.be/RwybCIHj0JE

Job Portal (PHP) - Part 12 - Validations & Code Improvements - https://youtu.be/mpO1j16udzM

Job Portal (PHP) - Part 13 - Email Sending Bug Fix - https://youtu.be/5ONR88bt0bY

Job Portal (PHP) - Part 14 - Search Highlighting & Forgot Password - https://youtu.be/HR7tvK5oO1g

Job Portal (PHP) - Part 15 - Select Company Location & Fixed Experience Filter - https://youtu.be/0mDXlpOulWc

Job Portal (PHP) - Part 16 - Theme Update Introduction - https://youtu.be/Lm5I6SSgJAw

Job Portal (PHP) - Part 17 - Homepage, Login & Registration Updated To New Theme - https://youtu.be/6neTJ6QRH6U

Job Portal (PHP) - Part 18 - Company Registration & Login Updated To New Theme - https://youtu.be/WJrQTybFQxo

Job Portal (PHP) - Part 19 - Updated Create Job Post & View Company Job Post - https://youtu.be/PK3Q9aAba-0

Job Portal (PHP) - Part 20 - Job Post Pagination & Apply To Job Post - https://youtu.be/Qrtnglv5N10

Job Portal (PHP) - Part 21 - Job Search Filters - https://youtu.be/upGiQeC3F9c

Job Portal (PHP) - Part 22 - Company Viewing & Marking Job Applications (Under Review/Rejected) - https://youtu.be/LgMaVxdf4Zs

Job Portal (PHP) - Part 23 - Company Candidate Interaction (Mailbox System) - https://youtu.be/TcouLN03LBY

Job Portal (PHP) - Part 24 - Bug Fix & Finishing Company & User Dashboard - https://youtu.be/GirgTCEilg8

Job Portal (PHP) - Part 25 - Admin Panel (Series Completed) - https://youtu.be/FaPCvXgjk-c

# Website Testing

Download the latest database.sql file.

There are 100 candidate users, 100 companies account & 1 admin account.
There are 100 dummy job posts added by random companies.

Step 1: Create a database called jobportal and import everything from database.sql file. Next check your db.php file for database connection configuration

```php
//Your db.php Mysql Config
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "jobportal";
```

Step2: Now you login as candidate with following details

```php
Email: oleg@test.com
Password: 123456
//Note1: There are 100 candadates users all with same password-123456
//Note2: All Password are encrpyted through code so you CANNOT change password directly from database.
```

Step3: Now you login as Company with following details

```php
Email: lobortis@a.ca
Password: 123456
//Note1: There are 100 Companies account all with same password-123456
//Note2: All Password are encrpyted through code so you CANNOT change password directly from database.
```

Step4: Now you login as Admin with following details

```php
Username: admin
Password: 123456
//Note: Password is not encrpyted from code so you CAN change directly from database.
```

Candidates Email Confirmation:
>You CANNOT send emails from localhost server. So when you create a new candidate account it will not send any emails. So you must go to database, find that user and set ```active=1``` in order to make that account login. 

>If you are testing on real server then you can uncomment the following code from ```adduser.php```

```php
// Send Email
$to = {CANDIDATE_EMAIL ADDRESS};
$subject = "Job Portal - Confirm Your Email Address";
$message = '
    <html>
    	 <head>
		    <title>Confirm Your Email</title>
		</head>
		<body>
		    <p>Click Link To Confirm</p>
		    <a href="{YOUR_REAL_DOMAIL}/verify.php?token='.$hash.'&email='.$email.'">Verify Email</a>
		</body>
	</html>
';
$headers[] = 'MIME-VERSION: 1.0';
$headers[] = 'Content-type: text/html; charset=iso-8859-1';
$headers[] = 'To: '.$to;
$headers[] = 'From: hello@yourdomain.com';
// You can add more headers like Cc, Bcc;
$result = mail($to, $subject, $message, implode("\r\n", $headers)); // \r\n will return new line. 
if($result === TRUE) {
//If email sent successfully then Set some session variables and redirect to login page
	$_SESSION['registerCompleted'] = true;
	header("Location: login.php");
	exit();
}
```

# Contact
Feel free to contact me through my website http://learningfromscratch.online/ 
>If you are following this tutorial series I would appritiate if you can subscribe and like my videos as it will keep me motivated to share my knowledge with you all!

# Contribution
Some Validations Added By Gunesh Shanbhag (gshanbhag525)

# Free Git-Training for Newbies
https://try.github.io/levels/1/challenges/1
