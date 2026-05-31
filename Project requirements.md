**Project requirements**

# **![][image1]**

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
| Free | $0 / forever | Browse jobs, save up to 10 jobs, basic profile, email notifications |
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

| Plan | Price | Apply to Jobs | Saved Jobs | Job Posts | Analytics |
| ----- | ----- | ----- | ----- | ----- | ----- |
| Free | $0 | ✗ (view only) | Up to 10 | ✗ | ✗ |
| Pro | $29/mo | ✓ Unlimited | ✓ Unlimited | ✗ | ✗ |
| Enterprise | $99/mo | ✓ Unlimited | ✓ Unlimited | ✓ Unlimited | ✓ |

Payment is processed via **Stripe**. All plans support upgrade/downgrade at any time with prorated billing. A 14-day money-back guarantee applies to paid plans.

[image1]: <data:image/png;base64,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>
