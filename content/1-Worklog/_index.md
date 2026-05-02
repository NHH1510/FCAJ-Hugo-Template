---
title : "Worklog"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

### Week 1
**Tasks:**
- Got familiar with the project and worked with the team to divide tasks.  
- Analyzed system requirements (music streaming web)  
- Studied overall architecture: Frontend – Backend – AWS  
- Set up development environment:
  - Node.js  
  - AWS account (Lambda, API Gateway, DynamoDB)  
- Researched RESTful API design principles  

**Achievements:**
- Clearly understood my role: responsible for Artists + Albums module  
- Gained an overview of system data flow  
- Ready to start backend development  

---

### Week 2
**Tasks:**
- Designed schema for Artists:
  - id, name, image, genre  
- Created DynamoDB table (partition key: artist_id)  
- Implemented Lambda functions:
  - getArtists  
  - getArtistById  
- Integrated with API Gateway  
- Tested APIs using Postman  

**Achievements:**
- Completed APIs:
  - GET /artists  
  - GET /artists/{id}  
- APIs return correct JSON format  
- Artists backend is stable  

---

### Week 3
**Tasks:**
- Designed schema for Albums:
  - id, title, artist_id, release_date, image  
- Created DynamoDB table for Albums  
- Implemented APIs:
  - GET /albums  
  - GET /artists/{id}/albums  
- Optimized query using artist_id  
- Tested integration with Artists module  

**Achievements:**
- Completed Albums backend module  
- Artist-based query works correctly  
- Successfully linked Artists and Albums data  

---

### Week 4
**Tasks:**
- Set up frontend (React)  
- Built Artists list page  
- Fetched data from backend API (/artists)  
- Displayed:
  - Artist name  
  - Artist image  
- Configured routing `/artists/:id`  

**Achievements:**
- Successfully displayed Artists on UI  
- Frontend and backend integration works properly  
- Data flow is correct  

---

### Week 5
**Tasks:**
- Built UI to display Albums by Artist  
- Fetched API `/artists/{id}/albums`  
- Rendered Albums list:
  - Cover image  
  - Title  
- Improved UI/UX (layout, spacing)  

**Achievements:**
- Albums displayed correctly by Artist  
- Improved user interface clarity  
- Data synced properly with backend  

---

### Week 6
**Tasks:**
- Built Artist detail page:
  - Artist info + albums list  
- Built Album detail page  
- Implemented dynamic routing:
  - `/artists/:id`  
  - `/albums/:id`  
- Added loading state handling  

**Achievements:**
- Completed detail view features  
- Improved user experience  
- Navigation flow is complete  

---

### Week 7
**Tasks:**
- Debugged and fixed issues:
  - CORS  
  - API errors  
  - undefined data  
- Refactored code:
  - Component separation  
  - Code cleanup  
- Optimized performance:
  - Reduced API calls  
  - Improved state management  

**Achievements:**
- System became more stable  
- Reduced runtime errors  
- Code is more maintainable  

---

### Week 8
**Tasks:**
- Deployed backend:
  - AWS Lambda + API Gateway  
- Deployed frontend:
  - S3 / GitHub Pages  
- Performed end-to-end testing:
  - Frontend ↔ Backend  
- Fixed production issues (CORS, endpoints)  
- Worked on the project using Hugo and prepared the internship report.

**Achievements:**
- Artists + Albums module runs in production environment  
- Successfully integrated with team system  
- Completed assigned personal contribution  