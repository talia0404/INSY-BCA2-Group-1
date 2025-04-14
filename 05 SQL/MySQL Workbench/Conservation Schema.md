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

INSERT INTO Animals (AnimalName, Species, Population) VALUES
('African Elephant', 'Loxodonta africana', 415000),
('Bengal Tiger', 'Panthera tigris tigris', 2500),
('Panda', 'Ailuropoda melanoleuca', 1864),
('Gray Wolf', 'Canis lupus', 20000),
('Giant Panda', 'Ailuropoda melanoleuca', 1800);

INSERT INTO Habitats (HabitatName, Location) VALUES
('Savanna', 'Africa'),
('Tundra', 'North America'),
('Forest', 'China'),
('Woodlands', 'North America'),
('Mountain', 'Himalayas');

INSERT INTO ConservationEfforts (AnimalID, EffortDescription, EffortStatus) VALUES
(1, 'Habitat restoration and anti-poaching initiatives', 'Active'),
(2, 'Breeding programs and habitat protection', 'Active'),
(3, 'Protection and habitat restoration efforts', 'Active'),
(4, 'Wolf reintroduction programs and park protections', 'Ongoing'),
(5, 'Research and breeding programs', 'Active');

```
