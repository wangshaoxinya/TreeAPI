# TreeAPI
智慧树轻量学习自动化接口工具
一款极简、轻量的智慧树接口集成项目，基于官方原生接口请求，批量获取密钥、学校信息、课程数据、作业题目列表，实现学习任务自动化处理，告别重复繁琐的手动操作。
# 项目简介
TreeAPI 整合了智慧树常用网关接口，通过标准 HTTP 请求实现学习数据抓取与任务自动化操作，适配日常课程、作业相关辅助场景，高效简化重复性学习操作，接口稳定、轻量化、无冗余依赖。
- 获取服务端用户专属密钥（SL值）
- 查询用户学校信息、学校ID数据
- 拉取课程详细信息、课程基础参数
- 获取作业列表、作业状态、题目信息
- 解析题目内容、提交作业作答数据
# 核心接口清单
1. 获取用户SL密钥
接口地址：https://appcomm-user.zhihuishu.com/app-commserv-user/c/has
请求方式：GET
接口说明：获取服务端返回的 SL 密钥，当前密钥为固定值，后续官方可能更新迭代
请求参数：
- uid：用户唯一ID（必填，URL拼接传参）
2. 获取学校信息
接口地址：https://studentexam-api.zhihuishu.com/studentExam/gateway/t/v1/exam/getLoginSchoolInfo
请求方式：POST
接口说明：获取当前登录账号对应的学校ID、学校基础信息，为其他接口提供必备参数
3. 获取课程信息
接口地址：https://onlineservice-api.zhihuishu.com/gateway/t/v1/student/course/share/queryShareCourseInfo
请求方式：POST
接口说明：查询并拉取用户已选课程的详细数据，获取课程核心参数
4. 获取作业列表
接口地址：https://studentexam-api.zhihuishu.com/studentExam/gateway/t/v1/student/getStudentHomework
请求方式：POST
接口说明：批量获取用户全部作业记录、作业完成状态、题目关联参数等核心数据
5. 题目获取 / 作业提交
接口地址：https://studentexam-api.zhihuishu.com/studentExam/gateway/t/v1/student/doHomework
请求方式：POST
接口说明：解析作业题目详情，支持提交作业答案，完成作业任务处理
# 必填请求参数：
- recruitId：
- examId：
- studentExamId：
- schoolId：学校ID
- courseId：课程ID
  
# 标准调用流程
1. 调用【获取用户SL密钥】接口，获取服务端核心密钥参数
2. 调用【获取学校信息】接口，拿到当前账号对应的 schoolId
3. 调用【获取课程信息】接口，获取 courseId、recruitId 等课程参数
4. 调用【获取作业列表】接口，拉取 examId、studentExamId 作业参数
5. 调用【题目获取/作业提交】接口，完成题目解析与作业提交
   
# 注意事项
- 所有接口均需携带完整请求头、登录Cookie、Token鉴权参数，无鉴权将请求失败
- 接口请求失败、解析异常，多为参数缺失、Token过期、官方接口更新导致，可核对参数或更新鉴权信息
- 本项目仅用于个人技术学习、代码研究，禁止用于违规操作与商业用途
- 官方接口可能不定期更新，若接口失效，需重新抓包适配最新接口参数
  
# 项目标签
#接口开发 #自动化工具 #学习辅助 #智慧树API
