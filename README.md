# Musical-World
Musical World is a web application that basically alow user to ulpoad their own songs and can listen to already uploaded songs and can add their song into favorite list.
This project contains admin side as well as user side.
User has to first register to the portal before uploading songs.
The account verification mechanism have been included in the project to verify user authentication.

*create database named "musical_world" at back-end and import the code tables.sql file inside databse folder to get access to database*

This is basically my DBMS mini project.
The site basically includes triggers and procedures.
So before running the application create a trigger and a procedure at back-end(xampp or wamp any application).

Code for triggers and procedure are given below.

****Trigger code****

*trigger to keep track of user contributions*
```mysql
CREATE TRIGGER `IncrementCount` AFTER INSERT ON `upload_albums`
 FOR EACH ROW update user set user.contributions = user.contributions + 1 where new.singer_id = user.user_id
 ```
 ****procedure code****
 
 *stored procedure to upload songs*
 ```mysql
 DELIMITER $$
CREATE DEFINER=`root`@`localhost` PROCEDURE `uploadsongs`(IN `singer_id` INT(11), IN `song_name` VARCHAR(255), IN `song_format` VARCHAR(255), IN `singer_name` VARCHAR(255), IN `song_image` VARCHAR(255), IN `audio_file` VARCHAR(255))
    NO SQL
INSERT INTO upload_albums(`singer_id`,`song_name`,`song_format`,`singer_name`,`song_image`,`audio_file`) VALUES(singer_id,song_name,song_format,singer_name,song_image,audio_file)$$
DELIMITER ;
```
```

