README.md
TreeAPI
Lightweight WisdomTree Study API Automation Tool
A simple, lightweight API interface integration project for daily learning auxiliary operations. Batch obtain course information, homework data, school information and complete task processing based on official interface requests.
✨ Project Introduction
TreeAPI integrates common official gateway interfaces of Wisdom Tree. It realizes data acquisition and automatic processing of learning tasks through standard HTTP requests, which greatly simplifies repetitive learning operations.
- Obtain user key information
- Query school & course details
- Fetch homework & question list data
- Submit homework task
📡 Interface List
1. Get User SL Key
URL：https://appcomm-user.zhihuishu.com/app-commserv-user/c/has
Method：GET
Description：Obtain server-side SL key (fixed at present, may be updated later)
Params：
- uid：User unique ID
2. Get School Info
URL：https://studentexam-api.zhihuishu.com/studentExam/gateway/t/v1/exam/getLoginSchoolInfo
Method：POST
Description：Get user’s corresponding school ID and school basic information
3. Get Course Info
URL：https://onlineservice-api.zhihuishu.com/gateway/t/v1/student/course/share/queryShareCourseInfo
Method：POST
Description：Query and obtain detailed course data
4. Get Homework List
URL：https://studentexam-api.zhihuishu.com/studentExam/gateway/t/v1/student/getStudentHomework
Method：POST
Description：Get all homework records, task status and question list information
5. Submit Homework / Get Question Detail
URL：https://studentexam-api.zhihuishu.com/studentExam/gateway/t/v1/student/doHomework
Method：POST
Description：Obtain question details and submit homework answers
Required Params：
- recruitId
- examId
- studentExamId
- schoolId
- courseId

⚠️ Notes
- All interfaces require complete request headers, cookies and token authentication
- Interface failure may be caused by invalid parameters, expired tokens or official interface updates
- This project is for personal learning and technical research only
📌 Tags
#API #Automation #StudyTool #WisdomTree
