

**1. Movie should have multiple media**
```sql
-- create MOVIE
CREATE TABLE MOVIE (
  id INT NOT NULL,
  mov_title TEXT NOT NULL,
  mov_year INT NOT NULL,
  duration_min INT NOT NULL,
  language TEXT NOT NULL
);

INSERT INTO MOVIE VALUES (1, 'Vaali', 1999, 159, 'Tamil');
INSERT INTO MOVIE VALUES (2, 'Kanchana', 2011, 160, 'Tamil');
INSERT INTO MOVIE VALUES (3, 'Nandha', 2001, 180, 'Tamil');
INSERT INTO MOVIE VALUES (4, 'Mersal', 2017, 168, 'Tamil');
INSERT INTO MOVIE VALUES (5, 'Indian', 1996, 185, 'Tamil');
INSERT INTO MOVIE VALUES (6, 'Ghilli', 2004, 167, 'Tamil');
INSERT INTO MOVIE VALUES (7, '24', 2016, 204, 'Tamil');
INSERT INTO MOVIE VALUES (8, 'Iru Mugan', 2016, 174, 'Tamil');
INSERT INTO MOVIE VALUES (9, 'Kochadaiiyaan', 2014, 118, 'Tamil');
INSERT INTO MOVIE VALUES (10, '13B', 2009, 177, 'Tamil');
INSERT INTO MOVIE VALUES (11, 'Aayirathil Oruvan', 2010, 182, 'Tamil');
INSERT INTO MOVIE VALUES (12, 'Maanaadu', 2012, 187, 'Tamil');
INSERT INTO MOVIE VALUES (13, 'Jeans', 1998, 212, 'Tamil');
INSERT INTO MOVIE VALUES (14, '96', 2018, 196, 'Tamil');
INSERT INTO MOVIE VALUES (15, 'Rocketry', 2022, 157, 'Tamil');

-- create Movie_media
CREATE TABLE Movie_media (
  med_id INT NOT NULL,
  mov_id INT NOT NULL,
  actor_name TEXT NOT NULL,
  director TEXT NOT NULL,
  music TEXT NOT NULL
);

INSERT INTO Movie_media VALUES (101, 1, 'Ajith', 'S.J.Suryah', 'Deva');
INSERT INTO Movie_media VALUES (102, 2, 'Lawrence', 'Lawrence', 'Thaman');
INSERT INTO Movie_media VALUES (103, 3, 'Surya', 'Bala', 'Yuvan');
INSERT INTO Movie_media VALUES (104, 4, 'Vijay', 'Atlee', 'A.R.Rahman');
INSERT INTO Movie_media VALUES (105, 5, 'Kamal', 'Shankar', 'A.R.Rahman');
INSERT INTO Movie_media VALUES (106, 6, 'Vijay', 'Dharani', 'Vidyasagar');
INSERT INTO Movie_media VALUES (107, 7, 'Surya', 'Vikram Kumar', 'A.R.Rahman');
INSERT INTO Movie_media VALUES (108, 8, 'Vikram', 'Anand Shankar', 'Harris Jayaraj');
INSERT INTO Movie_media VALUES (109, 9, 'Rajini', 'Soundarya', 'A.R.Rahman');
INSERT INTO Movie_media VALUES (110, 10, 'Madhavan', 'Vikram Kumar', 'Shankar Mahadevan');
INSERT INTO Movie_media VALUES (111, 11, 'Karthi', 'Selvaraghavan', 'G.V.Prakash');
INSERT INTO Movie_media VALUES (112, 12, 'Simbu', 'Venkat Prabhu', 'Yuvan');
INSERT INTO Movie_media VALUES (113, 13, 'Prashanth', 'Shankar', 'A.R.Rahman');
INSERT INTO Movie_media VALUES (114, 14, 'Vijay Sethupathi', 'Prem Kumar', 'Govind Vasantha');
INSERT INTO Movie_media VALUES (115, 15, 'Madhavan', 'R. Madhavan', 'Sam C.S.');

-- fetch 
SELECT * FROM Movie 
LEFT JOIN Movie_media 
ON 
Movie.id=Movie_media.mov_id;

```

**2. Movie can belongs to multiple Genres**
```sql
-- create MOVIE
CREATE TABLE MOVIE (
  id INT NOT NULL,
  mov_title TEXT NOT NULL,
  mov_year INT NOT NULL,
  duration_min INT NOT NULL,
  language TEXT NOT NULL
);

INSERT INTO MOVIE VALUES (1, 'Vaali', 1999, 159, 'Tamil');
INSERT INTO MOVIE VALUES (2, 'Kanchana', 2011, 160, 'Tamil');
INSERT INTO MOVIE VALUES (3, 'Nandha', 2001, 180, 'Tamil');
INSERT INTO MOVIE VALUES (4, 'Mersal', 2017, 168, 'Tamil');
INSERT INTO MOVIE VALUES (5, 'Indian', 1996, 185, 'Tamil');
INSERT INTO MOVIE VALUES (6, 'Ghilli', 2004, 167, 'Tamil');
INSERT INTO MOVIE VALUES (7, '24', 2016, 204, 'Tamil');
INSERT INTO MOVIE VALUES (8, 'Iru Mugan', 2016, 174, 'Tamil');
INSERT INTO MOVIE VALUES (9, 'Kochadaiiyaan', 2014, 118, 'Tamil');
INSERT INTO MOVIE VALUES (10, '13B', 2009, 177, 'Tamil');
INSERT INTO MOVIE VALUES (11, 'Aayirathil Oruvan', 2010, 182, 'Tamil');
INSERT INTO MOVIE VALUES (12, 'Maanaadu', 2012, 187, 'Tamil');
INSERT INTO MOVIE VALUES (13, 'Jeans', 1998, 212, 'Tamil');
INSERT INTO MOVIE VALUES (14, '96', 2018, 196, 'Tamil');
INSERT INTO MOVIE VALUES (15, 'Rocketry', 2022, 157, 'Tamil');

-- create genres
CREATE TABLE genres (
  gen_id int NOT NULL,
  mov_id INT NOT NULL,
  gen_title TEXT NOT NULL
);

-- insert
INSERT INTO genres VALUES (1001, 1, 'Romance');
INSERT INTO genres VALUES (1002, 2, 'Horror');
INSERT INTO genres VALUES (1003, 3, 'Drama');
INSERT INTO genres VALUES (1004, 4, 'Action');
INSERT INTO genres VALUES (1005, 5, 'Crime');
INSERT INTO genres VALUES (1006, 6, 'Comedy');
INSERT INTO genres VALUES (1007, 7, 'Sci-fi');
INSERT INTO genres VALUES (1008, 8, 'Thriller');
INSERT INTO genres VALUES (1009, 9, 'Animation');
INSERT INTO genres VALUES (1010, 10, 'Mystery');
INSERT INTO genres VALUES (1011, 11, 'Adventure');
INSERT INTO genres VALUES (1012, 12, 'Sci-fi');
INSERT INTO genres VALUES (1013, 13, 'Romance');
INSERT INTO genres VALUES (1014, 14, 'Romance');
INSERT INTO genres VALUES (101, 15, 'Biography');


-- fetch 
SELECT * FROM Movie 
INNER JOIN genres 
ON 
Movie.id=genres.mov_id;
```

**3. Movie can have multiple reviews and Review can belongs to a user**
```sql
-- create MOVIE
CREATE TABLE MOVIE (
  id INT NOT NULL,
  mov_title TEXT NOT NULL,
  mov_year INT NOT NULL,
  duration_min INT NOT NULL,
  language TEXT NOT NULL
);

INSERT INTO MOVIE VALUES (1, 'Vaali', 1999, 159, 'Tamil');
INSERT INTO MOVIE VALUES (2, 'Kanchana', 2011, 160, 'Tamil');
INSERT INTO MOVIE VALUES (3, 'Nandha', 2001, 180, 'Tamil');
INSERT INTO MOVIE VALUES (4, 'Mersal', 2017, 168, 'Tamil');
INSERT INTO MOVIE VALUES (5, 'Indian', 1996, 185, 'Tamil');
INSERT INTO MOVIE VALUES (6, 'Ghilli', 2004, 167, 'Tamil');
INSERT INTO MOVIE VALUES (7, '24', 2016, 204, 'Tamil');
INSERT INTO MOVIE VALUES (8, 'Iru Mugan', 2016, 174, 'Tamil');
INSERT INTO MOVIE VALUES (9, 'Kochadaiiyaan', 2014, 118, 'Tamil');
INSERT INTO MOVIE VALUES (10, '13B', 2009, 177, 'Tamil');
INSERT INTO MOVIE VALUES (11, 'Aayirathil Oruvan', 2010, 182, 'Tamil');
INSERT INTO MOVIE VALUES (12, 'Maanaadu', 2012, 187, 'Tamil');
INSERT INTO MOVIE VALUES (13, 'Jeans', 1998, 212, 'Tamil');
INSERT INTO MOVIE VALUES (14, '96', 2018, 196, 'Tamil');
INSERT INTO MOVIE VALUES (15, 'Rocketry', 2022, 157, 'Tamil');

-- create Rating
CREATE TABLE Rating (
  id INT NOT NULL,
  mov_id INT NOT NULL,
  rev_stars INT NOT NULL,
  num_o_users_rate INT NOT NULL
);

INSERT INTO Rating VALUES (301, 1, 8.40, 263575);
INSERT INTO Rating VALUES (302, 2, 7.90, 20207);
INSERT INTO Rating VALUES (303, 3, 8.30, 202778);
INSERT INTO Rating VALUES (304, 4, 8.20, 484746);
INSERT INTO Rating VALUES (305, 5, 9.00, 563575);
INSERT INTO Rating VALUES (306, 6, 8.60, 779489);
INSERT INTO Rating VALUES (307, 7, 7.40, 227235);
INSERT INTO Rating VALUES (308, 8, 4.40, 195961);
INSERT INTO Rating VALUES (309, 9, 5.40, 203875);
INSERT INTO Rating VALUES (310, 10, 3.40, 81328);
INSERT INTO Rating VALUES (311, 11, 8.50, 580301);
INSERT INTO Rating VALUES (312, 12, 8.80, 609451);
INSERT INTO Rating VALUES (313, 13, 9.20, 667758);
INSERT INTO Rating VALUES (314, 14, 8.60, 511613);
INSERT INTO Rating VALUES (315, 15, 6.70, 13091);

-- fetch 
SELECT * FROM Movie 
INNER JOIN Rating 
ON 
Movie.id=Rating.mov_id;
```

**4. Artist can have multiple skills**
```sql
-- create ACTOR
CREATE TABLE ACTOR (
  id int NOT NULL,
  act_name TEXT NOT NULL
);

-- insert
INSERT INTO ACTOR VALUES (0001, 'Ajith');
INSERT INTO ACTOR VALUES (0002, 'Kamal');
INSERT INTO ACTOR VALUES (0003, 'Lawrence');
INSERT INTO ACTOR VALUES (0004, 'Vijay');
INSERT INTO ACTOR VALUES (0005, 'Surya');
INSERT INTO ACTOR VALUES (0006, 'Dhanush');
INSERT INTO ACTOR VALUES (0007, 'Simbu');

-- create act_skills
CREATE TABLE act_skills (
  act_id int NOT NULL,
  Skills TEXT NOT NULL
);

INSERT INTO act_skills VALUES (0001, 'Actor, Car_Racer');
INSERT INTO act_skills VALUES (0002, 'Actor, Singer, Filmmaker, Politician');
INSERT INTO act_skills VALUES (0003, 'Actor, Dancer');
INSERT INTO act_skills VALUES (0004, 'Actor, Singer, Dancer');
INSERT INTO act_skills VALUES (0005, 'Actor, Producer');
INSERT INTO act_skills VALUES (0006, 'Actor, Singer, Director');
INSERT INTO act_skills VALUES (0007, 'Actor, Dancer, Singer');

-- fetch 
SELECT * FROM Actor 
INNER JOIN act_skills 
ON 
Actor.id=act_skills.act_id;
```

 **5. Artist can perform multiple role in a single film**
 ```sql
 -- create MOVIE
CREATE TABLE MOVIE (
  id INT NOT NULL,
  mov_title TEXT NOT NULL,
  mov_year INT NOT NULL,
  duration_min INT NOT NULL,
  language TEXT NOT NULL
);

INSERT INTO MOVIE VALUES (1, 'Vaali', 1999, 159, 'Tamil');
INSERT INTO MOVIE VALUES (2, 'Kanchana', 2011, 160, 'Tamil');
INSERT INTO MOVIE VALUES (3, 'Nandha', 2001, 180, 'Tamil');
INSERT INTO MOVIE VALUES (4, 'Mersal', 2017, 168, 'Tamil');
INSERT INTO MOVIE VALUES (5, 'Indian', 1996, 185, 'Tamil');
INSERT INTO MOVIE VALUES (6, 'Ghilli', 2004, 167, 'Tamil');
INSERT INTO MOVIE VALUES (7, '24', 2016, 204, 'Tamil');
INSERT INTO MOVIE VALUES (8, 'Iru Mugan', 2016, 174, 'Tamil');
INSERT INTO MOVIE VALUES (9, 'Kochadaiiyaan', 2014, 118, 'Tamil');
INSERT INTO MOVIE VALUES (10, '13B', 2009, 177, 'Tamil');
INSERT INTO MOVIE VALUES (11, 'Aayirathil Oruvan', 2010, 182, 'Tamil');
INSERT INTO MOVIE VALUES (12, 'Maanaadu', 2012, 187, 'Tamil');
INSERT INTO MOVIE VALUES (13, 'Jeans', 1998, 212, 'Tamil');
INSERT INTO MOVIE VALUES (14, '96', 2018, 196, 'Tamil');
INSERT INTO MOVIE VALUES (15, 'Rocketry', 2022, 157, 'Tamil');

-- create roll
CREATE TABLE roll (
  mov_id INT NOT NULL,
  actor TEXT NOT NULL,
  roll_1 TEXT NOT NULL,
  roll_2 TEXT NOT NULL
);

INSERT INTO roll VALUES (1, 'Ajith', 'Shiva', 'Deva');
INSERT INTO roll VALUES (4, 'Vijay', 'Maran', 'Vetri');
INSERT INTO roll VALUES (5, 'Kamal', 'Senapathy', 'Chandru');
INSERT INTO roll VALUES (8, 'Vikram', 'Akhilan', 'Vinod');
INSERT INTO roll VALUES (13, 'Prasanth', 'Vishvanathan', 'Ramamoorthy');

-- fetch 
SELECT * FROM Movie 
LEFT JOIN roll 
ON 
Movie.id=roll.mov_id;
```