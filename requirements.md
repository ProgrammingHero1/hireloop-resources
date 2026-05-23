# Project Requirements

<!-- Page 1 -->

Project  requirements    
 
The  Modern  Job  Hunting  Portal  
 
Overview  
HireLoop  is  a  full-featured  job  hunting  portal  that  bridges  the  gap  between  job  seekers  
and
 
employers.
 
It
 
streamlines
 
job
 
discovery,
 
application
 
management,
 
and
 
company
 
recruitment
 
—
 
all
 
in
 
one
 
platform.
 
It  oﬀers  smart  job  search,  company  proﬁles,  subscription-based  premium  features,  and  
a
 
recruiter
 
toolkit,
 
enhancing
 
hiring
 
speed
 
and
 
candidate
 
experience.
 
Designed  for  both  individuals  and  organizations,  HireLoop  simpliﬁes  the  talent  
acquisition
 
process
 
while
 
ensuring
 
a
 
transparent,
 
fast,
 
and
 
data-driven
 
hiring
 
experience.
 
 
User  Roles  
The  HireLoop  system  is  built  around  three  core  user  roles  —  Seeker ,  Recruiter ,  and  
Admin
 
—
 
each
 
responsible
 
for
 
distinct
 
parts
 
of
 
the
 
hiring
 
workﬂow.
 
Their
 
coordinated
 
interactions
 
ensure
 
a
 
seamless
 
end-to-end
 
job
 
marketplace
 
experience.
 
 
👤  1.  Seeker  
Seekers  are  registered  job  hunters  who  use  HireLoop  to  discover  and  apply  for  
opportunities.
 
Their
 
responsibilities
 
include:


---

<!-- Page 2 -->

-  Creating  and  maintaining  a  personal  proﬁle  with  skills,  and  contact  details.  -  Browsing  and  searching  jobs  with  advanced  ﬁlters  (location,  salary,  type,  etc.).  -  Saving  favorite  jobs  for  later  review.  -  Applying  to  jobs  directly  through  the  platform  (requires  a  paid  plan).  -  Tracking  the  status  of  submitted  applications  from  the  dashboard.  -  Upgrading  to  a  Pro  or  Enterprise  subscription  to  unlock  premium  features.  
 
🏢  2.  Recruiter  
Recruiters  are  company  representatives  who  source  and  hire  talent  through  HireLoop.  
Their
 
key
 
functions
 
include:
 
-  Registering  and  managing  a  company  proﬁle  on  the  platform.  -  Posting,  editing,  and  removing  job  listings  tied  to  their  company.  -  Reviewing  and  managing  incoming  applications  for  each  job  post.  -  Viewing  analytics  on  job  post  performance  and  applicant  activity.  
 
🛠  3.  Admin  
Admins  are  platform  operators  responsible  for  ensuring  the  quality  and  integrity  of  the  
HireLoop
 
ecosystem.
 
Their
 
key
 
functions
 
include:
 
-  Managing  all  registered  users  (Seekers  and  Recruiters)  with  role  control.  -  Reviewing,  approving,  or  rejecting  company  registrations  submitted  by  
Recruiters.
 -  Monitoring  and  moderating  all  job  listings  across  the  platform.  -  Viewing  platform-wide  analytics  including  user  growth,  job  post  counts,  and  
revenue.
 -  Managing  subscription  plans  and  payment  records.  
 
Dashboard  Requirements  
Layouts  
The  system  will  have  a  Responsive  Dashboard  consistent  across  all  roles.


---

<!-- Page 3 -->

A  Sidebar  at  the  Left:  
-  Contains  the  HireLoop  logo,  user  info  (Name,  Avatar,  Email,  Role).  -  Dynamic  navigation  links  based  on  the  logged-in  user's  role.  -  Navigation  links  to  public  pages  (Home,  Browse  Jobs,  Companies,  Pricing).  -  A  Logout  Button  —  clicking  it  ends  the  session  and  redirects  to  the  homepage.  
Pages  at  the  Right:  
-  Pages  are  rendered  dynamically  based  on  the  current  route.  
 
Public  Pages  
Home  Page  
-  Hero  section  with  headline,  subheadline,  and  CTA  buttons  ("Search  Jobs",  "Post  a  
Job").
 -  Live  stats:  Active  Jobs,  Companies,  Job  Seekers,  Satisfaction  Rate.  -  Featured  Jobs  section  with  hand-picked  listings  in  card  format.  -  Platform  features  section  highlighting  Smart  Search,  Salary  Insights,  Top  
Companies,
 
and
 
Saved
 
Jobs.
 -  Footer  with  navigation  links  for  Job  Seekers,  Employers,  and  Company  info.  
Browse  Jobs  (/jobs)  
-  A  search  bar  with  keyword  input.  -  Filter  sidebar  with  options  for  job  type,  location,  salary  range,  and  category.  -  Job  listing  cards  displaying:  title,  company,  location,  type,  and  salary  range.  -  Clicking  a  job  card  navigates  to  the  Job  Details  page.  
Companies  (/companies)  
-  Displays  all  registered  and  approved  companies  in  a  card  grid.  -  Filter  tabs  by  industry  (e.g.,  Fintech,  AI,  Developer  Tools,  E-Commerce,  etc.).  -  Each  company  card  shows:  logo/avatar,  name,  industry,  location,  employee  
count,
 
and
 
number
 
of
 
open
 
jobs.
 -  Clicking  a  company  card  navigates  to  that  company's  proﬁle  page.  
Pricing  (/pricing)


---

<!-- Page 4 -->

-  Three  subscription  tiers  displayed  in  card  format:  
Plan  Price  Key  Features  
Free  $0  /  forever  Browse  jobs,  save  up  to  10  jobs,  basic  proﬁle,  email  notiﬁcations  
Pro  $29  /  month  Unlimited  applications  &  saved  jobs,  priority  applications,  application  tracking,  salary  insights  
Enterprise  $99  /  month  Everything  in  Pro  +  unlimited  job  posts,  ATS,  team  collaboration,  analytics  dashboard,  dedicated  support,  custom  branding  
-  FAQ  accordion  section  covering  cancellation,  refunds,  payment  methods,  and  
plan
 
switching.
 
Job  Details  Page  (/jobs/:jobId)  
-  Full  job  description,  responsibilities,  and  requirements.  -  Company  info  card  with  logo,  name,  and  location.  -  Salary  range  and  job  type  badge.  -  Apply  button  (requires  login  and  paid  plan  for  Seekers).  -  Similar  job  suggestions  at  the  bottom.  
 
Seeker  Dashboard  
Seeker  Home  
Stats  Row:  Display  counts  for  —  Saved  Jobs,  Applications  Submitted,  Interviews  
Scheduled,
 
Oﬀers
 
Received.
 
Recharts  &  Proﬁle  Card:  
-  Left:  User  proﬁle  card  showing  name,  email,  photo  URL,  and  an  Edit  button.  -  Right:  A  Pie  Chart  or  Bar  Chart  showing  application  status  distribution  (Applied,  
Under
 
Review,
 
Shortlisted,
 
Rejected,
 
Oﬀered).
 
Recent  Activity:  A  notiﬁcation-style  list  of  recent  application  updates  and  job  alerts.


---

<!-- Page 5 -->

Browse  &  Apply  (/dashboard/jobs)  
-  Full  job  search  experience  within  the  dashboard.  -  Filters  for  job  type,  location,  salary,  and  category.  -  Each  listing  has  a  Save  button  and  an  Apply  button.  -  The  apply  button  triggers  a  modal  to  conﬁrm  the  application  or  upload  a  cover  
letter.
 
 
Saved  Jobs  (/dashboard/saved)  
-  Displays  all  jobs  the  Seeker  has  bookmarked.  -  Table/card  format  with:  job  title,  company,  location,  salary,  date  saved.  -  Each  row  has  a  Remove  button  and  an  Apply  button.  
 
My  Applications  (/dashboard/applications)  
-  Table  of  all  submitted  applications.  -  Columns:  Job  Title,  Company,  Date  Applied,  Status  (Applied  /  Under  Review  /  
Shortlisted
 
/
 
Rejected
 
/
 
Oﬀered).
 -  Each  row  has  a  View  Details  button  linking  to  the  job  listing.  -  Date  shown  in  relative  format  (e.g.,  "5  days  ago").  
 
Subscription  &  Billing  (/dashboard/billing)  
-  Shows  the  Seeker's  current  plan  (Free  /  Pro  /  Enterprise).  -  Upgrade/Downgrade  buttons  linking  to  the  Pricing  page.  -  Payment  history  table  with:  Date,  Plan,  Amount,  Transaction  ID.  -  Stripe-integrated  card  payment  on  upgrade.  -  On  successful  payment:  save  payment  record,  activate  the  new  plan,  show  a  
success
 
toast.
 
 
Seeker  Settings  (/dashboard/settings)


---

<!-- Page 6 -->

-  Update  proﬁle  info:  name,  email,  avatar/photo  URL,  password.  -  Upload  or  update  resume  (PDF).  -  Add/edit  skills,  headline,  and  bio.  
 
Recruiter  Dashboard  
Recruiter  Home  
Stats  Row:  Total  Job  Posts,  Total  Applicants,  Active  Jobs,  Jobs  Closed.  
Recharts  &  Company  Card:  
-  Left:  Company  proﬁle  card  (name,  logo,  industry)  with  Edit  button.  -  Right:  Bar  chart  showing  applicant  count  per  job  post  over  the  last  30  days.  
Recent  Applications:  A  notiﬁcation-style  list  of  the  latest  applicants  across  all  job  
posts.
 
 
My  Company  (/dashboard/company)  
-  If  no  company  is  registered:  Show  a  prompt  and  a  "Register  Company"  button.  -  If  registered:  Show  company  details  —  name,  logo,  industry,  location,  employee  
count,
 
description.
 -  Edit  button  to  update  company  information.  -  Company  status  badge:  Pending  /  Approved  /  Rejected  (set  by  Admin).  
Register  /  Edit  Company  Form  
Fields:  
-  Company  Name,  Industry/Category,  Website  URL  -  Location,  Employee  Count  Range  -  Company  Logo  (image  upload)  -  Short  Description  
On  submit:  save  to  database  with  status  pending.  Admin  must  approve  before  the  
company
 
appears
 
publicly.


---

<!-- Page 7 -->

Manage  Jobs  (/dashboard/manage-jobs)  
-  Table  of  all  job  posts  created  by  the  Recruiter.  -  Columns:  Job  Title,  Status  (Active  /  Closed  /  Draft),  Applicants  Count,  Date  
Posted.
 -  Action  buttons  per  row:  Edit,  View  Applicants,  Close/Reopen,  Delete  (with  
conﬁrmation).
 -  A  "Post  New  Job"  button  at  the  top  navigating  to  the  Add  Job  page.  
 
Post  a  Job  (/dashboard/post-job)  
A  form  divided  into  sections:  
Job  Info:  
-  Job  Title,  Job  Category,  Job  Type  (Full-time  /  Part-time  /  Remote  /  Contract  /  
Internship)
 -  Salary  Range  (Min  &  Max),  Currency  -  Location  (City,  Country)  or  Remote  toggle  -  Application  Deadline  
Job  Description:  
-  Responsibilities  (rich  text  or  textarea)  -  Requirements  (rich  text  or  textarea)  -  Beneﬁts  (optional)  
Company:  Auto-ﬁlled  from  the  Recruiter's  registered  company  (must  be  approved  to  
post).
 
On  submit:  save  job  with  status  active,  link  to  Recruiter's  company,  and  make  it  publicly  
visible.
 
 
View  Applicants  (/dashboard/jobs/:jobId/applicants)  
-  List  of  all  Seekers  who  applied  for  a  speciﬁc  job.


---

<!-- Page 8 -->

-  Table  columns:  Applicant  Name,  Email,  Date  Applied,  Resume  link,  Status.  -  Status  dropdown  per  applicant:  Applied  →  Under  Review  →  Shortlisted  →  
Rejected
 
→
 
Oﬀered.
 -  Changing  status  sends  an  email  notiﬁcation  to  the  applicant.  
 
Recruiter  Settings  (/dashboard/settings)  
-  Update  personal  info:  name,  email,  avatar,  password.  -  Manage  linked  company  (redirect  to  My  Company  page).  
 
Admin  Dashboard  
Admin  Home  
Stats  Row:  Total  Users,  Total  Recruiters,  Total  Companies,  Total  Jobs  Posted,  Platform  
Revenue.
 
Recharts:  
-  Bar  chart  of  job  posts  per  category.  -  Line  chart  of  new  user  registrations  over  the  past  30  days.  
Recent  Payments:  Notiﬁcation-style  list  of  the  latest  subscription  transactions.  
 
Manage  Users  (/admin/users)  
-  Search  bar  ﬁltering  by  email  address.  -  Filter  dropdown  by  role  (Seeker  /  Recruiter).  -  Table  of  all  platform  users:  Name,  Email,  Role,  Join  Date,  Status.  -  Action  buttons:    -  Make  Recruiter  (if  currently  Seeker)  —  with  conﬁrmation  alert.    -  Make  Seeker  (if  currently  Recruiter)  —  with  conﬁrmation  alert.    -  Suspend  /  Activate  account.


---

<!-- Page 9 -->

Manage  Companies  (/admin/companies)  
-  Table  of  all  company  registrations.  -  Columns:  Company  Name,  Recruiter  Email,  Industry,  Status  (Pending  /  Approved  /  
Rejected),
 
Date
 
Submitted.
 -  Conditional  action  buttons:    -  Approve  (if  status  is  Pending  or  Rejected)  —  sets  status  to  approved,  
company
 
becomes
 
publicly
 
visible.
   -  Reject  (if  status  is  Pending  or  Approved)  —  sets  status  to  rejected,  
company
 
is
 
removed
 
from
 
public
 
listing.
 
 
Manage  Jobs  (/admin/jobs)  
-  Search  bar  ﬁltering  by  job  title  or  company  name.  -  Filter  by  job  status  (Active  /  Closed)  and  category.  -  Table  of  all  job  posts:  Title,  Company,  Category,  Type,  Date  Posted,  Status.  -  Action  buttons:  View  (go  to  job  details),  Remove  (delete  with  conﬁrmation).  
 
Payment  &  Subscriptions  (/admin/payments)  
-  Table  of  all  subscription  payments  across  the  platform.  -  Columns:  User  Email,  Plan,  Amount,  Date,  Transaction  ID,  Status.  -  Date  shown  in  both  absolute  and  relative  format  (e.g.,  "May  10,  2026  ·  9  days  
ago").
 -  Summary  cards  at  the  top:  Total  Revenue,  Monthly  Revenue,  Active  Pro  Users,  
Active
 
Enterprise
 
Users.
 
 
Admin  Settings  (/admin/settings)  
-  Update  admin  proﬁle:  name,  email,  avatar,  password.  
 
Parcel  Status  Flow  (Application  Status  Flow)  
Job  Posted  →  Seeker  Applies  →  Under  Review  →  Shortlisted  →  Oﬀered  /  Rejected


---

<!-- Page 10 -->

Application  Status  
Status  Description  
Applied  Seeker  has  submitted  an  application  
Under  Review  Recruiter  has  started  reviewing  the  application  
Shortlisted  Candidate  has  been  shortlisted  for  interview  
Rejected  Application  has  been  declined  
Oﬀered  Candidate  has  received  a  job  oﬀer  
Company  Status  
Status  Description  
Pending  Company  registration  submitted,  awaiting  admin  review  
Approved  Company  veriﬁed  and  publicly  visible  
Rejected  Company  registration  declined  by  Admin   
Subscription  Plans  
Plan  Price  Apply  to  Jobs  
Saved  Jobs  
Job  Posts  Analytics  
Free  $0  ✗  (view  only)  
Up  to  10  ✗  ✗  
Pro  $29/mo  
✓  Unlimited  
✓  Unlimited  
✗  ✗


---

<!-- Page 11 -->

Enterprise  
$99/mo  
✓  Unlimited  
✓  Unlimited  
✓  Unlimited  
✓  
Payment  is  processed  via  Stripe .  All  plans  support  upgrade/downgrade  at  any  time  with  
prorated
 
billing.
 
A
 
14-day
 
money-back
 
guarantee
 
applies
 
to
 
paid
 
plans.
