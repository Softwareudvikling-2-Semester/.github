## Opsætning af vores MySQL database 👋

CREATE DATABASE students_db;

USE students_db;

CREATE TABLE students_db.teams (
team_id INT AUTO_INCREMENT PRIMARY KEY,
team_name VARCHAR(255)
);

CREATE TABLE students_db.events (
event_id INT AUTO_INCREMENT PRIMARY KEY,
event_name VARCHAR(255)
);

CREATE TABLE students_db.students (
student_id INT AUTO_INCREMENT PRIMARY KEY,
first_name VARCHAR(255),
last_name VARCHAR(255),
card_uid VARCHAR(255),
team_id INT,
FOREIGN KEY (team_id) REFERENCES students_db.teams(team_id)
);

CREATE TABLE students_db.event_student (
student_id int,
event_id int,
is_checked_in bool
);

