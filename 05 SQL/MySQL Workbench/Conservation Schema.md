```sql
CREATE DATABASE ---DB

USE Database;

CREATE TABLE Animals (
    AnimalID INT AUTO_INCREMENT PRIMARY KEY,
    AnimalName VARCHAR(100) NOT NULL,
    Species VARCHAR(100) NOT NULL,
    Population INT NOT NULL
);

CREATE TABLE Habitats (
    HabitatID INT AUTO_INCREMENT PRIMARY KEY,
    HabitatName VARCHAR(100) NOT NULL,
    Location VARCHAR(100) NOT NULL
);

CREATE TABLE ConservationEfforts (
    EffortID INT AUTO_INCREMENT PRIMARY KEY,
    AnimalID INT,
    EffortDescription VARCHAR(500),
    EffortStatus VARCHAR(100),
    FOREIGN KEY (AnimalID) REFERENCES Animals(AnimalID)
);
```
