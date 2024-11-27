# adopteundev

#### ---Les entitées et leurs attributs--- #####
[User] 

*id (PK)
email
password
role
created_at

[Developer]

*id (PK, FK -> User.id)
first_name
last_name
location
bio
salary_expectation
avatar
experience_level

[Company]

*id (PK, FK -> User.id)
name
location
description

[JobOffer]

*id (PK)
title
description
location
salary_range
experience_required
created_at
company_id (FK -> Company.id)

[Technology]

*id (PK)
name

[Developer_Technology]

*developer_id (FK -> Developer.id)
*technology_id (FK -> Technology.id)

[JobOffer_Technology]

*job_offer_id (FK -> JobOffer.id)
*technology_id (FK -> Technology.id)

[Match]

*id (PK)
developer_id (FK -> Developer.id)
job_offer_id (FK -> JobOffer.id)
created_at

[Rating]

*id (PK)
developer_id (FK -> Developer.id)
rating
comment

[Favorite]

*id (PK)
user_id (FK -> User.id)
developer_id (FK -> Developer.id, nullable)
job_offer_id (FK -> JobOffer.id, nullable)

##### ----Realtions entre les entitées---- ######

User *--1 Developer

User *--1 Company

Company 1--* JobOffer

Developer *--* Technology

JobOffer *--* Technology

Developer 1--* Match

JobOffer 1--* Match

Developer 1--* Rating

User 1--* Favorite
Developer 1--* Favorite
JobOffer 1--* Favorite
