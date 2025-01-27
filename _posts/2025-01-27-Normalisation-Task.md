---
layout: post
title: Normalisation Task 
subtitle: Normalising data to 3rd Form (3NF)
categories: 
tags: [normalisation]
---

## How I normalised the dataset: demonstration of 1NF, 2NF and 3NF. 

Please have a look at the dataset I need to normalise here. 
[DBD_PCOM7E Table.xlsx](https://github.com/user-attachments/files/18564688/DBD_PCOM7E.Table.xlsx)

The fist normal form [1NF] is achieved by elimination of repeated groups and ensuring atomic values. We can see that initially the data is grouped by student name and there are multiple values in course column. 

![Before1NF](https://github.com/user-attachments/assets/f98e6431-be85-472a-bcbe-8fc048d9beb3)

To achieve [1NF] I restructured data to make sure there is only one value per cell. Like this. 

![AfterN1](https://github.com/user-attachments/assets/963638ff-875b-498f-b1db-a5eb6c9ba8c9)

To achieve [2NF] we need to get rid of redundancies. After ensuring [1NF] we have student name multiple times as well as course instructor. The course instructor is repeated for each course. The problem with that is that it is redundant and inefficient. To achieve [2NF] these partial dependencies had to be fixed by decomposing one table into three: student table (student number PK, student name), course name (course name PK, course instructor), and enrollment table (student number, course name, enrollment date where student number and course name make up the composite key). With this split of tables each table has attributes dependent on Primary Key hence there are no partial dependencies.

To achieve [3NF] we have to eliminate transitive dependency which means breaking data even further. Teacher name while related to course is not tied to student number and depends on the course name which creates transitive dependency. This can be fixed by separating teacher's information as a separate table in order to link course name and teacher's name. After addressing [3NF] we have four tables: student, courses, enrollment and teachers. This prevents redundancy and elimiinates duplication. 



