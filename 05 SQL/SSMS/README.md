# Activity:

```sql
--Create a database Named FestivalDB
CREATE DATABASE FestivalDBGr1

--Use the created database
USE FestivalDBGr1

--Create the USER Table
CREATE TABLE FestivalUser(
UserID INT IDENTITY(1,1) PRIMARY KEY, --(1,1) First value is what the attrribute begins at, the second value is the increment value
FirstName VARCHAR(50) NOT NULL,
LastName VARCHAR(50) NOT NULL
)

SELECT * FROM FestivalUser;

CREATE TABLE Festival(
FestivalID INT IDENTITY(1,1) PRIMARY KEY,
FestivalName VARCHAR(100) NOT NULL,
FestivalLocation VARCHAR(100) NOT NUll,
StartDate DATE NOT NULL,
EndDate DATE NOT NULL
)
SELECT * FROM Festival;

CREATE TABLE Artist(
ArtistID INT IDENTITY(1,1) PRIMARY KEY,
StageName VARCHAR(50) NOT NULL,
Genre VARCHAR(50) NOT NULL
)
SELECT * FROM Artist

--Creating a table with foreign keys
CREATE TABLE FestivalArtist(
FestivalArtistID INT IDENTITY(1,1) PRIMARY KEY,
FestivalID INT NOT NULL,
ArstistID INT NOT NULL,

FOREIGN KEY (FestivalID) REFERENCES Festival(FestivalID),
FOREIGN KEY (ArstistID) REFERENCES Artist(ArtistID)
)
SELECT * FROM FestivalArtist

CREATE TABLE Ticket(
TicketID INT IDENTITY(1,1) PRIMARY KEY,
PurchaseDate DATE NOT NULL,
TicketPrice DECIMAL(5,2) NOT NULL,
FestivalUserID INT NOT NULL,
FestivalID INT NOT NULL,

FOREIGN KEY (FestivalUserID) REFERENCES FestivalUser(UserID),
FOREIGN KEY (FestivalID) REFERENCES Festival(FestivalID)
)

SELECT * FROM Ticket

---- Insert data into the Festival table
INSERT INTO Festival (Name, Location, StartDate, EndDate)
VALUES 
    ('Rock Fest 2025', 'New York, USA', '2025-06-15', '2025-06-18'),
    ('Electronic Waves', 'Berlin, Germany', '2025-07-10', '2025-07-12'),
    ('Jazz Harmony', 'Cape Town, South Africa', '2025-08-05', '2025-08-07');

INSERT INTO Artist (StageName, Genre)
VALUES 
    ('The Thunder Band', 'Rock'),
    ('DJ Sonic', 'Electronic'),
    ('Smooth Sax', 'Jazz');

-- Linking Artists to Festivals
INSERT INTO FestivalArtists (FestivalID, ArtistID)
VALUES 
    (1, 1),
    (2, 2),
    (3, 3);

INSERT INTO User (FirstName, LastName)
VALUES 
    ('Alice', 'Johnson'),
    ('Bob', 'Smith'),
    ('Charlie', 'Brown');

INSERT INTO Ticket (PurchaseDate, TicketPrice, UserID, FestivalID)
VALUES 
    ('2025-05-10', 120.00, 1, 1),
    ('2025-06-20', 150.00, 2, 2),
    ('2025-07-30', 100.00, 3, 3);
```

## 20 March

1. Use SSMS.

2. Create a new Query.

3. Create a new database.

4. Use the Activity 2 ERD to create tables in a database.

5. Add at least 1 value in each table.


