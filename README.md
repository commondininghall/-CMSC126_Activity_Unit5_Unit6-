# <CMSC126_Activity_Unit5_Unit6>
# Team Members:
  * Edriellen Mey Cambel - Project Lead / Frontend Developer
  * Mikaela Kristen De Guzman - Backend Developer / System Analyst
  * Trisha Mae Hechenagocia - Database Administrator / QA Engineer

# Project Description:
The legacy system currently suffers from many issues such as outdated architecture, dead links, and a cluttered interface.

UPV CRS 2.0 is an improved version of the University of the Philippines Visayas. Computerized Registration System — the main platform serving the university's  students, faculty, and administrators. This version aims to provide a cleaner, more modern experience by addressing the shortcomings of the current system through updated architecture and a smoother, more intuitive interface.

Additional Features:
	* Automated Email Notification 
      * Students automatically receive notification to their emails regarding enrollment status and accountabilities.		
    * UP Mail SSO (Single Sign-On) Authentication Scheme 
      * Allows students log in using their UP Mail account instead of manually entering their student number and password.

  
# Tech Stack:
###  Frontend Tools:
* Next.js – Ensures sensitive student data is fetched on the server rather than the browser to prevent unauthorized users, especially                                         tech-savvy students, from finding private API calls.

* Tailwind CSS – Helps with designing dashboards and web apps by providing professional-looking components to work with.

* React Hook Form + Zod – Makes sure input data is perfectly and neatly formatted to prevent “junk data” from reaching the database.
    
###  Backend Tools:
* Clerk – Allows to define user permissions to enable/disable permissions depending on the type of user.

* TanStack Query – Allows automatic refresh of web pages whenever a data is updated, for example, when a teacher uploads a student’s grades.
    
###  Database:
* PostgreSQL – Ensures ACID compliance is strictly regulated.

* Supabase (Database, Storage, Authentication)- for database, uses PostgreSQL, row level security
    
### Other Tools:
   * Cloud Storage (AWS S3) – Handles storage of Student Photos and Enrollment Forms.
   
   * Vercel – Allows preview deployments for testing of new features in a private link.
   
   * Resend – Allows sending of automated emails for reminders, like of a student’s enrollment status for instance.

# Hosting (Platform for hosting)
A hybrid hosting approach is implemented using three specific platforms with each one having a specific responsibilty: Vercel (frontend and backend), Supabase (database), AWS S3 (file storage). 

### Vercel — Frontend and Backend
  
#### What it hosts: 
  * All pages of site and UI
  * Backend logic — form submissions, login processingm role verification
  * Server-side, rendering, API routes, Clerk authentication, React Query
  
#### Why it was chosen:
  * Built by the same team as Next.js — everything is optimized and reliable 
  * Automatically scales during pre-registraion season traffic spikes
  * Supports up to 30,000 simultaneous actions and 1TB data transfer per month — more than enough for the estimated 3,000-student population requirement
  * Deployments are automated – code updates go live immediately after push

### Supabase — Database
  
#### What it hosts: 
  * PostgreSQL database
  * Stundet, faculty, admin records
  * Academic transactions and data
  * Schedulings
  
#### Why it was chosen:
  * Fully managed — no separate database server to maintain 
  * Row-level security — users can only access data they are permitted to see
  * Supports complex queries across interconnected tables
  * ACID compliant – transactions are processed reliably while maintaining data integrity

### AWS S3 — File Storage

#### What it hosts: 
 * Downloadable PDF forms
 * Academic calendars and official documents
 * Student-uploaded files such as profile photos
  
#### Why it was chosen:
 * Files delivered directly to users without passing through the application server — keeps Vercel bandwidth consumption low 
 * Extremely high reliability and low cost sizes 


