# Examination of Facebook Database System
![facebook](https://github.com/user-attachments/assets/5751b79f-3f7f-4928-ae33-409232c916ae)

## Description
_This project focuses on analyzing Facebook's database system to understand how it supports the platform’s extensive features and operations. Facebook's database is designed to handle a variety of user activities, such as messaging, posting, reacting, commenting, and participating in marketplace transactions. In addition to these core features, the platform also incorporates other functionalities like gaming and live streaming, all of which rely on efficient data management and integration. By studying the database structure and its functionalities, this project provides valuable insights into the underlying mechanisms that make these diverse features possible and operational._

_Within Facebook's database, numerous entities are defined, including users, accounts, admins, posts, comments, ads, games, and streams. The relationships among these entities are carefully structured to facilitate efficient data storage and retrieval. For instance, user accounts are linked to activities like posting content, saving ads, and engaging with other users’ posts. Admin functionalities are also integrated, enabling moderators to manage inappropriate content across posts, ads, or streams. These well-defined relationships ensure smooth interactions across the platform, maintaining data integrity and supporting Facebook's vast user base._

To further understand the effectiveness of Facebook’s database system, key queries and reports used within the platform are analyzed. For example, the system is capable of identifying saved ads for a specific user, retrieving comments on a post, calculating earnings for eligible streamers, and determining the most engaged users in games. These reports, which are generated from the data queries, provide actionable insights that help in optimizing the platform, identifying user preferences, and evaluating content performance. As a result, Facebook can offer a more personalized experience for its users based on their behaviors and interactions.

This analysis underscores the complexity and efficiency of Facebook's database system, which supports millions of daily interactions. By understanding the structure and functionality of the database, the project highlights the critical role of data management in sustaining such a multifaceted platform. The insights gained from this study offer valuable lessons in designing scalable and efficient database systems that can support large-scale applications, ensuring they are capable of handling the diverse and ever-evolving needs of users.

## Overview
```
SELECT User.User_Name, Posts.Post_ID, Posts.Published_at FROM User
INNER JOIN Posts ON Posts.User_ID = User.User_ID
WHERE User.User_ID = 4 AND Posts.Post_Type = 3
ORDER BY Posts.Published_at DESC;
```
_Users save the ads they like and Facebook stores them in their database. This query is used to list which adds a specific user saved. Saved_Ads and User tables are used for this query._
```
SELECT Posts.Post_ID, User.User_Name, Comments.Content FROM (Comments INNER JOIN User ON User.User_ID = Comments.User_ID)
INNER JOIN Posts ON Posts.Post_ID = Comments.Post_ID
WHERE Posts.Post_ID = 5;
```
_Users can comment on different users' posts and when a user clicks on any post while browsing Facebook, they see these comments. Thanks to this query, related comments are displayed under the relevant post._
```
SELECT User.User_Name AS [Streamer Name], SUM(Stream.Total_Earning) AS Amount_To_Be_Paid FROM (Streamer INNER JOIN User ON Streamer.User_ID = User.User_ID)
INNER JOIN Stream ON Streamer.Streamer_ID = Stream.Streamer_ID
GROUP BY User.User_Name HAVING SUM(Stream.Total_Earning) > 100;
```
_Facebook pays streamers who earn over $100 per month at the end of the month. This query determines which streamers are eligible and how much should be paid. User, Streamer, Stream tables and aggregate function are used for this query._

## Contributors
_Can Erbaşoğlu_

_Efe Murat Uçarlı (https://github.com/efemuratucarli)_

_Kağan Turhan (https://github.com/kaganturhan)_

_Osman Batuhan İnalöz (https://github.com/ydsaglme)_
