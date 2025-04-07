```SQL
CREATE DATABASE BookReviewDB;

USE BookReviewDB;

CREATE TABLE BookReviewUser(
UserID INT AUTO_INCREMENT PRIMARY KEY,
FirstName VARCHAR(100) NOT NULL,
LastName VARCHAR(100) NOT NULL
);

INSERT INTO BookReviewUser(FirstName, LastName)
VALUES
('Joseph','Smith'
);

SELECT * FROM BookReviewUser;

CREATE TABLE ReadingList(
ReadingListID INT AUTO_INCREMENT PRIMARY KEY,
Name VARCHAR(50) NOT NULL,
UserID1 INT NOT NULL,
FOREIGN KEY (UserID1) REFERENCES BookReviewUser(UserID)
);

ALTER TABLE ReadingList
CHANGE Name ReadingListName VARCHAR(50) NOT NULL;

SELECT * FROM ReadingList

ALTER TABLE ReadingList
DROP COLUMN ReadingListName

ALTER TABLE ReadingList
ADD COLUMN ReadingListName VARCHAR(50) NOT NUll

CREATE TABLE Book(
BookID INT AUTO_INCREMENT PRIMARY KEY,
Title VARCHAR(50) NOT NUll,
Author VARCHAR(50)NOT NUll,
PublicationYear VARCHAR(4) NOT NUll,
UserID INT NOT NUll,
ReadListID INT NOT NUll,
FOREIGN KEY (UserID) REFERENCES BookReviewUser(UserID),
FOREIGN KEY (ReadListID) REFERENCES ReadingList(ReadingListID)
);

CREATE TABLE Review(
ReviewID INT AUTO_INCREMENT PRIMARY KEY,
Rating VARCHAR(1) NOT NUll,
ReviewDescription VARCHAR(500) NOT NUll,
ReviewDate DATE NOT NUll, -- 'yyyy-mm-dd'
UserID INT NOT NUll,
BookID INT NOT NUll,
FOREIGN KEY (UserID) REFERENCES BookReviewUser(UserID),
FOREIGN KEY (BookID) REFERENCES Book(BookID)
);

-- add values/records into the book table and review table

INSERT INTO ReadingList(ReadingListName, UserID1)
VALUES
('Summer Reads', 1),
('Winter Classics', 1);

SELECT * FROM ReadingList;


INSERT INTO Book(Title, Author, PublicationYear, UserID, ReadListID)
VALUES
('To Kill a Mockingbird', 'Harper Lee', '1960', 1, 1);

INSERT INTO Review(Rating, ReviewDescription, ReviewDate, UserID, BookID)
VALUES
('5', 'An outstanding novel with deep themes on morality and justice.', '2025-04-07', 1, 9);

SELECT * FROM Book;
SELECT * FROM Review;

-- updating values in table

UPDATE Book
SET PublicationYear = '1961'
WHERE BookID = 9;

# delete a record/value

DELETE FROM Review
WHERE ReviewID = 3;

DELETE FROM Book
WHERE BookID = 9;

```

