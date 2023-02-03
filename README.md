# VTA
Data and code for LittleMu: Deploying an Online Virtual Teaching Assistant via Heterogeneous Sources Integration and Chain-of-Teach Prompts.

# Data

To facilitate the development and evaluation for future VTA systems, we present the **VTA** dataset, which consists of 3 kinds of data: 

- human preference scores for different models
-  coarse-to-fine intention for history dialogues 
- reference answers for real questions. 

| Task                     | Courses | Participants | Label   |
| ------------------------ | ------- | ------------ | ------- |
| Intention Classification | 139     | 10           | 4,000   |
| Question Answering       | 139     | 10           | 1,767   |
| General Dialog           | 20      | 20           | 124,512 |

The data's download link will be available after we finish necessary anonymization:

- The data access permission is granted by XuetangX. We follow the privacy policy and protect the users' data by deploying our system on the company's intranet to prevent data leaking. Therefore, we should anonymize the user's name for the intention and QA data using real history dialogues. 

Here we share the collection process for VTA dataset:

- The annotation guideline for Intention Classification: https://kvbpkpddff.feishu.cn/docx/LsSkdZwOEoIBZCxeU0Wc414qnLd
- The annotation guideline for QA: https://kvbpkpddff.feishu.cn/docx/EOsJdZbIdoWrcqx0MwCcYRdtnHb
- The annotation guideline for General Dialog : https://kvbpkpddff.feishu.cn/docx/doxcn3OhKgFU0zPxDT0yiszULQh



# Code

For more deployment details, you can view this document: https://kvbpkpddff.feishu.cn/docx/doxcnCgjYpEK0ms7KCrEmBx2Iuc

- The retrieval module is implemented in this repository: http://xiaomu-student.xuetangx.com/gitlab/xuwei/xiaomu
  - As the retrieval module utilized course-specific data on XuetangX MOOC platform, we will check the privacy policy and release the visible database in next a few weeks.

- The generation module is  implemented in this repository: https://github.com/lcy2723/XDAI
  - The  generation module is implemented based on some code from https://github.com/THUDM/XDAI

# Milestones

We record our discussions, progresses and weekly plans in this document:

https://kvbpkpddff.feishu.cn/docx/doxcnbT70XKGLC1uTV19243bY0e
