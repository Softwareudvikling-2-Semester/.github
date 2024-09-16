# Mini projekt - scanning af studiekort 👋

## Vores arbejde består af 3 forskellige projekter

### CardScanner
Som bruger PCSC librariet til at scanne, og udtrække UID fra et studiekort, samt at sende dette videre i RabbitMQ

### DataEnricher
Som modtager UID fra studiekortet, og queryer vores database for oplysninger om den studerende, samt om den studerende er tjekke ind til event.

### Check-In-Frontend
Som giver feedback til brugeren, altså om den enkelte bruger er tjekket ind, eller om der skete fejl i løbet af processen.

Til opsætning af vores database har vi brugt følgende SQL:
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

