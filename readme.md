# Examination of Facebook Database System
<p align="center">
  <img width="886" height="158" src="https://github.com/user-attachments/assets/ade10a9c-dacd-4eb9-8d95-0c477576e235" alt="facebook">
</p>

![facebook](https://github.com/user-attachments/assets/1533fcbd-1880-476e-af97-0840fce81627)

## About Project
This project focuses on analyzing Facebook's database system to understand how it supports the platform’s extensive features and operations. Facebook's database is designed to handle a variety of user activities, including messaging, posting, reacting, commenting, and participating in marketplace transactions. The platform also incorporates additional features like gaming and live streaming, all of which rely on efficient data management and integration. By studying the database structure and functionality, the project provides insights into the underlying mechanisms that make these features possible.

The database includes numerous entities, such as users, accounts, admins, posts, comments, ads, games, and streams. Relationships among these entities are carefully defined to facilitate efficient data storage and retrieval. For instance, user accounts are linked to their activities like posting content, saving ads, and engaging with other users' content. Admin functionalities are also integrated into the database, enabling the moderation of inappropriate posts, ads, or streams. These relationships ensure seamless interactions across the platform while maintaining data integrity.

Key queries and reports used within Facebook's system are analyzed to understand how data is extracted and utilized. Examples include identifying saved ads for a specific user, retrieving comments on a post, calculating earnings for eligible streamers, and determining the most engaged users in games. Reports generated from these queries provide actionable insights, such as user preferences and content performance, which help optimize the platform and create more personalized experiences for users.

This analysis underscores the complexity and efficiency of Facebook's database system, which supports millions of daily interactions. By understanding the structure and functionality of the database, the project highlights the critical role data management plays in sustaining such a multifaceted platform. These insights offer valuable lessons in designing scalable and efficient database systems for large-scale applications.

## Sample Queries
```
SELECT User.User_Name AS [Streamer Name], SUM(Stream.Total_Earning) AS Amount_To_Be_Paid FROM (Streamer INNER JOIN User ON Streamer.User_ID = User.User_ID)
INNER JOIN Stream ON Streamer.Streamer_ID = Stream.Streamer_ID
GROUP BY User.User_Name HAVING SUM(Stream.Total_Earning) > 100 
```
_Facebook pays streamers who earn over $100 per month at the end of the month. This query determines which streamers are eligible and how much should be paid. User, Streamer, Stream tables and aggregate function are used for this query._

## Contributors
_Can Erbaşoğlu_

_Efe Murat Uçarlı (https://github.com/efemuratucarli)_

_Kağan Turhan (https://github.com/kaganturhan)_

_Osman Batuhan İnalöz (https://github.com/ydsaglme)_
