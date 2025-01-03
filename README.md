# Fitness-and-Diet-Planner
Personal Health and Fitness Management System This Java-based project allows users to manage health data, including step tracking, calorie intake, and exercise records. It uses MySQL for data storage and provides CRUD functionalities through a simple command-line interface.
create the Person table;
CREATE TABLE Person (
    id INT AUTO_INCREMENT PRIMARY KEY,
    userName VARCHAR(255) NOT NULL,
    age INT NOT NULL,
    height DOUBLE NOT NULL,
    weight DOUBLE NOT NULL,
    gender CHAR(1) NOT NULL CHECK (gender IN ('M', 'F')),
    dailystepstodo INT NOT NULL,
    dailycaloriesintake INT NOT NULL
);

create Meals table;
CREATE TABLE Meals (
    id INT AUTO_INCREMENT PRIMARY KEY,
    userId INT NOT NULL,
    meal VARCHAR(255) NOT NULL,
    calories INT NOT NULL,
    FOREIGN KEY (userId) REFERENCES Person(id)
);

create Exercise Table;
CREATE TABLE Exercises (
    id INT AUTO_INCREMENT PRIMARY KEY,
    userId INT NOT NULL,
    exerciseType VARCHAR(255) NOT NULL,
    calories INT NOT NULL,
    FOREIGN KEY (userId) REFERENCES Person(id)
);

