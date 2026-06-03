**Project requirements**

## **The Modern Job Hunting Portal**

---

## **Overview**

HireLoop is a full-featured job hunting portal that bridges the gap between job seekers and employers. It streamlines job discovery, application management, and company recruitment — all in one platform.

It offers smart job search, company profiles, subscription-based premium features, and a recruiter toolkit, enhancing hiring speed and candidate experience.

Designed for both individuals and organizations, HireLoop simplifies the talent acquisition process while ensuring a transparent, fast, and data-driven hiring experience.

---

## **User Roles**

The HireLoop system is built around three core user roles — **Seeker**, **Recruiter**, and **Admin** — each responsible for distinct parts of the hiring workflow. Their coordinated interactions ensure a seamless end-to-end job marketplace experience.

---

### **👤 1\. Seeker**

Seekers are registered job hunters who use HireLoop to discover and apply for opportunities. Their responsibilities include:

* Creating and maintaining a personal profile with skills, and contact details.  
* Browsing and searching jobs with advanced filters (location, salary, type, etc.).  
* Saving favorite jobs for later review.  
* Applying to jobs directly through the platform (requires a paid plan).  
* Tracking the status of submitted applications from the dashboard.  
* Upgrading to a Pro or Enterprise subscription to unlock premium features.

---

### **🏢 2\. Recruiter**

Recruiters are company representatives who source and hire talent through HireLoop. Their key functions include:

* Registering and managing a company profile on the platform.  
* Posting, editing, and removing job listings tied to their company.  
* Reviewing and managing incoming applications for each job post.  
* Viewing analytics on job post performance and applicant activity.

---

### **🛠️ 3\. Admin**

Admins are platform operators responsible for ensuring the quality and integrity of the HireLoop ecosystem. Their key functions include:

* Managing all registered users (Seekers and Recruiters) with role control.  
* Reviewing, approving, or rejecting company registrations submitted by Recruiters.  
* Monitoring and moderating all job listings across the platform.  
* Viewing platform-wide analytics including user growth, job post counts, and revenue.  
* Managing subscription plans and payment records.

---

## **Dashboard Requirements**

### **Layouts**

The system will have a **Responsive Dashboard** consistent across all roles.

**A Sidebar at the Left:**

* Contains the HireLoop logo, user info (Name, Avatar, Email, Role).  
* Dynamic navigation links based on the logged-in user's role.  
* Navigation links to public pages (Home, Browse Jobs, Companies, Pricing).  
* A Logout Button — clicking it ends the session and redirects to the homepage.

**Pages at the Right:**

* Pages are rendered dynamically based on the current route.

---

## **Public Pages**

### **Home Page**

* Hero section with headline, subheadline, and CTA buttons ("Search Jobs", "Post a Job").  
* Live stats: Active Jobs, Companies, Job Seekers, Satisfaction Rate.  
* Featured Jobs section with hand-picked listings in card format.  
* Platform features section highlighting Smart Search, Salary Insights, Top Companies, and Saved Jobs.  
* Footer with navigation links for Job Seekers, Employers, and Company info.

### **Browse Jobs (/jobs)**

* A search bar with keyword input.  
* Filter sidebar with options for job type, location, salary range, and category.  
* Job listing cards displaying: title, company, location, type, and salary range.  
* Clicking a job card navigates to the Job Details page.

### **Companies (/companies)**

* Displays all registered and approved companies in a card grid.  
* Filter tabs by industry (e.g., Fintech, AI, Developer Tools, E-Commerce, etc.).  
* Each company card shows: logo/avatar, name, industry, location, employee count, and number of open jobs.  
* Clicking a company card navigates to that company's profile page.

### **Pricing (/pricing)**

* Three subscription tiers displayed in card format:

| Plan | Price | Key Features |
| ----- | ----- | ----- |
| Free | $0 / forever | Browse jobs, apply up to 5 jobs, basic profile, email notifications |
| Pro | $29 / month | Unlimited applications & saved jobs, priority applications, application tracking, salary insights |
| Enterprise | $99 / month | Everything in Pro \+ unlimited job posts, ATS, team collaboration, analytics dashboard, dedicated support, custom branding |

* FAQ accordion section covering cancellation, refunds, payment methods, and plan switching.

### **Job Details Page (/jobs/:jobId)**

* Full job description, responsibilities, and requirements.  
* Company info card with logo, name, and location.  
* Salary range and job type badge.  
* Apply button (requires login and paid plan for Seekers).  
* Similar job suggestions at the bottom.

---

## **Seeker Dashboard**

### **Seeker Home**

**Stats Row:** Display counts for — Saved Jobs, Applications Submitted, Interviews Scheduled, Offers Received.

**Recharts & Profile Card:**

* Left: User profile card showing name, email, photo URL, and an Edit button.  
* Right: A Pie Chart or Bar Chart showing application status distribution (Applied, Under Review, Shortlisted, Rejected, Offered).

**Recent Activity:** A notification-style list of recent application updates and job alerts.

---

### **Browse & Apply (/dashboard/seeker/jobs)**

* Full job search experience within the dashboard.  
* Filters for job type, location, salary, and category.  
* Each listing has a Save button and an Apply button.  
* The apply button triggers a modal to confirm the application or upload a cover letter.

---

### **Saved Jobs (/dashboard/seeker/saved)**

* Displays all jobs the Seeker has bookmarked.  
* Table/card format with: job title, company, location, salary, date saved.  
* Each row has a Remove button and an Apply button.

---

### **My Applications (/dashboard/seeker/applications)**

* Table of all submitted applications.  
* Columns: Job Title, Company, Date Applied, Status (Applied / Under Review / Shortlisted / Rejected / Offered).  
* Each row has a View Details button linking to the job listing.  
* Date shown in relative format (e.g., "5 days ago").

---

### **Subscription & Billing (/dashboard/seeker/billing)**

* Shows the Seeker's current plan (Free / Pro / Enterprise).  
* Upgrade/Downgrade buttons linking to the Pricing page.  
* Payment history table with: Date, Plan, Amount, Transaction ID.  
* Stripe-integrated card payment on upgrade.  
* On successful payment: save payment record, activate the new plan, show a success toast.

---

### **Seeker Settings (/dashboard/seeker/settings)**

* Update profile info: name, email, avatar/photo URL, password.  
* Upload or update resume (PDF).  
* Add/edit skills, headline, and bio.

---

## **Recruiter Dashboard**

### **Recruiter Home**

**Stats Row:** Total Job Posts, Total Applicants, Active Jobs, Jobs Closed.

**Recharts & Company Card:**

* Left: Company profile card (name, logo, industry) with Edit button.  
* Right: Bar chart showing applicant count per job post over the last 30 days.

**Recent Applications:** A notification-style list of the latest applicants across all job posts.

---

### **My Company (/dashboard/recruiter/company)**

* If no company is registered: Show a prompt and a "Register Company" button.  
* If registered: Show company details — name, logo, industry, location, employee count, description.  
* Edit button to update company information.  
* Company status badge: Pending / Approved / Rejected (set by Admin).

### **Register / Edit Company Form**

Fields:

* Company Name, Industry/Category, Website URL  
* Location, Employee Count Range  
* Company Logo (image upload)  
* Short Description

On submit: save to database with status pending. Admin must approve before the company appears publicly.

---

### **Manage Jobs (/dashboard/recruiter/jobs)**

* Table of all job posts created by the Recruiter.  
* Columns: Job Title, Status (Active / Closed / Draft), Applicants Count, Date Posted.  
* Action buttons per row: Edit, View Applicants, Close/Reopen, Delete (with confirmation).  
* A "Post New Job" button at the top navigating to the Add Job page.

---

### **Post a Job (/dashboard/recruiter/jobs/new)**

A form divided into sections:

**Job Info:**

* Job Title, Job Category, Job Type (Full-time / Part-time / Remote / Contract / Internship)  
* Salary Range (Min & Max), Currency  
* Location (City, Country) or Remote toggle  
* Application Deadline

**Job Description:**

* Responsibilities (rich text or textarea)  
* Requirements (rich text or textarea)  
* Benefits (optional)

**Company:** Auto-filled from the Recruiter's registered company (must be approved to post).

On submit: save job with status active, link to Recruiter's company, and make it publicly visible.

---

### **View Applicants (/dashboard/jobs/:jobId/applicants)**

* List of all Seekers who applied for a specific job.  
* Table columns: Applicant Name, Email, Date Applied, Resume link, Status.  
* Status dropdown per applicant: Applied → Under Review → Shortlisted → Rejected → Offered.  
* Changing status sends an email notification to the applicant.

---

### **Recruiter Settings (/dashboard/recruiter/settings)**

* Update personal info: name, email, avatar, password.  
* Manage linked company (redirect to My Company page).

---

## **Admin Dashboard**

### **Admin Home**

**Stats Row:** Total Users, Total Recruiters, Total Companies, Total Jobs Posted, Platform Revenue.

**Recharts:**

* Bar chart of job posts per category.  
* Line chart of new user registrations over the past 30 days.

**Recent Payments:** Notification-style list of the latest subscription transactions.

---

### **Manage Users (/dashboard/admin/users)**

* Search bar filtering by email address.  
* Filter dropdown by role (Seeker / Recruiter).  
* Table of all platform users: Name, Email, Role, Join Date, Status.  
* Action buttons:  
  * Make Recruiter (if currently Seeker) — with confirmation alert.  
  * Make Seeker (if currently Recruiter) — with confirmation alert.  
  * Suspend / Activate account.

---

### **Manage Companies (/dashboard/admin/companies)**

* Table of all company registrations.  
* Columns: Company Name, Recruiter Email, Industry, Status (Pending / Approved / Rejected), Date Submitted.  
* Conditional action buttons:  
  * Approve (if status is Pending or Rejected) — sets status to approved, company becomes publicly visible.  
  * Reject (if status is Pending or Approved) — sets status to rejected, company is removed from public listing.

---

### **Manage Jobs (/dashboard/admin/jobs)**

* Search bar filtering by job title or company name.  
* Filter by job status (Active / Closed) and category.  
* Table of all job posts: Title, Company, Category, Type, Date Posted, Status.  
* Action buttons: View (go to job details), Remove (delete with confirmation).

---

### **Payment & Subscriptions (/dashboard/admin/payments)**

* Table of all subscription payments across the platform.  
* Columns: User Email, Plan, Amount, Date, Transaction ID, Status.  
* Date shown in both absolute and relative format (e.g., "May 10, 2026 · 9 days ago").  
* Summary cards at the top: Total Revenue, Monthly Revenue, Active Pro Users, Active Enterprise Users.

---

### **Admin Settings (/dashboard/admin/settings)**

* Update admin profile: name, email, avatar, password.

---

## **Application Status Flow**

Job Posted → Seeker Applies → Under Review → Shortlisted → Offered / Rejected

### **Application Status**

| Status | Description |
| ----- | ----- |
| Applied | Seeker has submitted an application |
| Under Review | Recruiter has started reviewing the application |
| Shortlisted | Candidate has been shortlisted for interview |
| Rejected | Application has been declined |
| Offered | Candidate has received a job offer |

### **Company Status**

| Status | Description |
| ----- | ----- |
| Pending | Company registration submitted, awaiting admin review |
| Approved | Company verified and publicly visible |
| Rejected | Company registration declined by Admin |

---

## **Subscription Plans**

| Plan | Price | Apply to Jobs | Apply Jobs | Job Posts | Analytics |
| ----- | ----- | ----- | ----- | ----- | ----- |
| Free | $0 | ✗ (view only) | Up to 10 | ✗ | ✗ |
| Pro | $29/mo | ✓ Unlimited | ✓ Unlimited | ✗ | ✗ |
| Enterprise | $99/mo | ✓ Unlimited | ✓ Unlimited | ✓ Unlimited | ✓ |

Payment is processed via **Stripe**. All plans support upgrade/downgrade at any time with prorated billing. A 14-day money-back guarantee applies to paid plans.
