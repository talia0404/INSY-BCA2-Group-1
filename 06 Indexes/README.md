# 🎢 **AdventureLand Database Indexing Activity**

**Instructions:**
You have been hired by AdventureLand to help improve the performance of their new database.
You must create appropriate **clustered and non-clustered indexes**, test them, and document your results.
Answer the following tasks by writing both the SQL code and explaining your results.

---



```sql
CREATE DATABASE AdventureLandDB;
USE AdventureLandDB;

-- Table: ParkRides
CREATE TABLE ParkRides (
    RideID INT PRIMARY KEY,
    RideName VARCHAR(255),
    RideType VARCHAR(50),
    Status VARCHAR(20),
    LastInspection DATETIME
);

-- Table: Visitors
CREATE TABLE Visitors (
    VisitorID INT PRIMARY KEY,
    FullName VARCHAR(255),
    MembershipType VARCHAR(20),
    LastVisit DATETIME
);

-- Table: RideQueue
CREATE TABLE RideQueue (
    QueueID INT PRIMARY KEY,
    VisitorID INT,
    RideID INT,
    QueueTime DATETIME
);

-- Table: RideIncidents
CREATE TABLE RideIncidents (
    IncidentID INT PRIMARY KEY,
    RideID INT,
    IncidentType VARCHAR(50),
    ReportedAt DATETIME
);

INSERT INTO ParkRides (RideID, RideName, RideType, Status, LastInspection) VALUES
(1, 'Ride 1', 'Haunted House', 'Maintenance', '2025-05-01 08:01:00'),
(2, 'Ride 2', 'Haunted House', 'Open', '2025-05-01 08:02:00'),
(3, 'Ride 3', 'Haunted House', 'Closed', '2025-05-01 08:03:00'),
(4, 'Ride 4', 'Ferris Wheel', 'Open', '2025-05-01 08:04:00'),
(5, 'Ride 5', 'Ferris Wheel', 'Open', '2025-05-01 08:05:00'),
(6, 'Ride 6', 'Water Ride', 'Open', '2025-05-01 08:06:00'),
(7, 'Ride 7', 'Haunted House', 'Maintenance', '2025-05-01 08:07:00'),
(8, 'Ride 8', 'Ferris Wheel', 'Closed', '2025-05-01 08:08:00'),
(9, 'Ride 9', 'Roller Coaster', 'Open', '2025-05-01 08:09:00'),
(10, 'Ride 10', 'Haunted House', 'Closed', '2025-05-01 08:10:00'),
(11, 'Ride 11', 'Water Ride', 'Open', '2025-05-01 08:11:00'),
(12, 'Ride 12', 'Roller Coaster', 'Closed', '2025-05-01 08:12:00'),
(13, 'Ride 13', 'Ferris Wheel', 'Open', '2025-05-01 08:13:00'),
(14, 'Ride 14', 'Haunted House', 'Maintenance', '2025-05-01 08:14:00'),
(15, 'Ride 15', 'Ferris Wheel', 'Maintenance', '2025-05-01 08:15:00'),
(16, 'Ride 16', 'Ferris Wheel', 'Closed', '2025-05-01 08:16:00'),
(17, 'Ride 17', 'Haunted House', 'Maintenance', '2025-05-01 08:17:00'),
(18, 'Ride 18', 'Water Ride', 'Closed', '2025-05-01 08:18:00'),
(19, 'Ride 19', 'Ferris Wheel', 'Maintenance', '2025-05-01 08:19:00'),
(20, 'Ride 20', 'Haunted House', 'Closed', '2025-05-01 08:20:00'),
(21, 'Ride 21', 'Haunted House', 'Closed', '2025-05-01 08:21:00'),
(22, 'Ride 22', 'Water Ride', 'Closed', '2025-05-01 08:22:00'),
(23, 'Ride 23', 'Haunted House', 'Maintenance', '2025-05-01 08:23:00'),
(24, 'Ride 24', 'Ferris Wheel', 'Closed', '2025-05-01 08:24:00'),
(25, 'Ride 25', 'Roller Coaster', 'Maintenance', '2025-05-01 08:25:00'),
(26, 'Ride 26', 'Ferris Wheel', 'Maintenance', '2025-05-01 08:26:00'),
(27, 'Ride 27', 'Ferris Wheel', 'Open', '2025-05-01 08:27:00'),
(28, 'Ride 28', 'Ferris Wheel', 'Open', '2025-05-01 08:28:00'),
(29, 'Ride 29', 'Haunted House', 'Open', '2025-05-01 08:29:00'),
(30, 'Ride 30', 'Haunted House', 'Closed', '2025-05-01 08:30:00'),
(31, 'Ride 31', 'Roller Coaster', 'Closed', '2025-05-01 08:31:00'),
(32, 'Ride 32', 'Roller Coaster', 'Open', '2025-05-01 08:32:00'),
(33, 'Ride 33', 'Roller Coaster', 'Maintenance', '2025-05-01 08:33:00'),
(34, 'Ride 34', 'Haunted House', 'Closed', '2025-05-01 08:34:00'),
(35, 'Ride 35', 'Roller Coaster', 'Maintenance', '2025-05-01 08:35:00'),
(36, 'Ride 36', 'Ferris Wheel', 'Maintenance', '2025-05-01 08:36:00'),
(37, 'Ride 37', 'Roller Coaster', 'Open', '2025-05-01 08:37:00'),
(38, 'Ride 38', 'Haunted House', 'Closed', '2025-05-01 08:38:00'),
(39, 'Ride 39', 'Haunted House', 'Open', '2025-05-01 08:39:00'),
(40, 'Ride 40', 'Water Ride', 'Closed', '2025-05-01 08:40:00'),
(41, 'Ride 41', 'Ferris Wheel', 'Open', '2025-05-01 08:41:00'),
(42, 'Ride 42', 'Ferris Wheel', 'Closed', '2025-05-01 08:42:00'),
(43, 'Ride 43', 'Haunted House', 'Closed', '2025-05-01 08:43:00'),
(44, 'Ride 44', 'Haunted House', 'Maintenance', '2025-05-01 08:44:00'),
(45, 'Ride 45', 'Water Ride', 'Maintenance', '2025-05-01 08:45:00'),
(46, 'Ride 46', 'Roller Coaster', 'Open', '2025-05-01 08:46:00'),
(47, 'Ride 47', 'Water Ride', 'Maintenance', '2025-05-01 08:47:00'),
(48, 'Ride 48', 'Ferris Wheel', 'Closed', '2025-05-01 08:48:00'),
(49, 'Ride 49', 'Ferris Wheel', 'Closed', '2025-05-01 08:49:00'),
(50, 'Ride 50', 'Roller Coaster', 'Closed', '2025-05-01 08:50:00'),
(51, 'Ride 51', 'Haunted House', 'Maintenance', '2025-05-01 08:51:00'),
(52, 'Ride 52', 'Roller Coaster', 'Open', '2025-05-01 08:52:00'),
(53, 'Ride 53', 'Haunted House', 'Open', '2025-05-01 08:53:00'),
(54, 'Ride 54', 'Haunted House', 'Maintenance', '2025-05-01 08:54:00'),
(55, 'Ride 55', 'Water Ride', 'Maintenance', '2025-05-01 08:55:00'),
(56, 'Ride 56', 'Haunted House', 'Open', '2025-05-01 08:56:00'),
(57, 'Ride 57', 'Water Ride', 'Closed', '2025-05-01 08:57:00'),
(58, 'Ride 58', 'Haunted House', 'Closed', '2025-05-01 08:58:00'),
(59, 'Ride 59', 'Water Ride', 'Maintenance', '2025-05-01 08:59:00'),
(60, 'Ride 60', 'Ferris Wheel', 'Maintenance', '2025-05-01 09:00:00'),
(61, 'Ride 61', 'Haunted House', 'Open', '2025-05-01 09:01:00'),
(62, 'Ride 62', 'Haunted House', 'Closed', '2025-05-01 09:02:00'),
(63, 'Ride 63', 'Haunted House', 'Open', '2025-05-01 09:03:00'),
(64, 'Ride 64', 'Haunted House', 'Closed', '2025-05-01 09:04:00'),
(65, 'Ride 65', 'Ferris Wheel', 'Open', '2025-05-01 09:05:00'),
(66, 'Ride 66', 'Water Ride', 'Closed', '2025-05-01 09:06:00'),
(67, 'Ride 67', 'Haunted House', 'Maintenance', '2025-05-01 09:07:00'),
(68, 'Ride 68', 'Ferris Wheel', 'Maintenance', '2025-05-01 09:08:00'),
(69, 'Ride 69', 'Water Ride', 'Maintenance', '2025-05-01 09:09:00'),
(70, 'Ride 70', 'Roller Coaster', 'Maintenance', '2025-05-01 09:10:00'),
(71, 'Ride 71', 'Roller Coaster', 'Open', '2025-05-01 09:11:00'),
(72, 'Ride 72', 'Haunted House', 'Open', '2025-05-01 09:12:00'),
(73, 'Ride 73', 'Water Ride', 'Open', '2025-05-01 09:13:00'),
(74, 'Ride 74', 'Water Ride', 'Closed', '2025-05-01 09:14:00'),
(75, 'Ride 75', 'Haunted House', 'Closed', '2025-05-01 09:15:00'),
(76, 'Ride 76', 'Water Ride', 'Open', '2025-05-01 09:16:00'),
(77, 'Ride 77', 'Haunted House', 'Maintenance', '2025-05-01 09:17:00'),
(78, 'Ride 78', 'Haunted House', 'Open', '2025-05-01 09:18:00'),
(79, 'Ride 79', 'Ferris Wheel', 'Maintenance', '2025-05-01 09:19:00'),
(80, 'Ride 80', 'Roller Coaster', 'Maintenance', '2025-05-01 09:20:00'),
(81, 'Ride 81', 'Water Ride', 'Maintenance', '2025-05-01 09:21:00'),
(82, 'Ride 82', 'Ferris Wheel', 'Maintenance', '2025-05-01 09:22:00'),
(83, 'Ride 83', 'Roller Coaster', 'Closed', '2025-05-01 09:23:00'),
(84, 'Ride 84', 'Water Ride', 'Open', '2025-05-01 09:24:00'),
(85, 'Ride 85', 'Water Ride', 'Open', '2025-05-01 09:25:00'),
(86, 'Ride 86', 'Ferris Wheel', 'Closed', '2025-05-01 09:26:00'),
(87, 'Ride 87', 'Roller Coaster', 'Open', '2025-05-01 09:27:00'),
(88, 'Ride 88', 'Ferris Wheel', 'Open', '2025-05-01 09:28:00'),
(89, 'Ride 89', 'Haunted House', 'Closed', '2025-05-01 09:29:00'),
(90, 'Ride 90', 'Roller Coaster', 'Maintenance', '2025-05-01 09:30:00'),
(91, 'Ride 91', 'Ferris Wheel', 'Maintenance', '2025-05-01 09:31:00'),
(92, 'Ride 92', 'Ferris Wheel', 'Maintenance', '2025-05-01 09:32:00'),
(93, 'Ride 93', 'Ferris Wheel', 'Closed', '2025-05-01 09:33:00'),
(94, 'Ride 94', 'Haunted House', 'Closed', '2025-05-01 09:34:00'),
(95, 'Ride 95', 'Haunted House', 'Maintenance', '2025-05-01 09:35:00'),
(96, 'Ride 96', 'Haunted House', 'Closed', '2025-05-01 09:36:00'),
(97, 'Ride 97', 'Haunted House', 'Open', '2025-05-01 09:37:00'),
(98, 'Ride 98', 'Ferris Wheel', 'Open', '2025-05-01 09:38:00'),
(99, 'Ride 99', 'Roller Coaster', 'Maintenance', '2025-05-01 09:39:00'),
(100, 'Ride 100', 'Roller Coaster', 'Closed', '2025-05-01 09:40:00');

INSERT INTO Visitors (VisitorID, FullName, MembershipType, LastVisit) VALUES
(1, 'Visitor 1', 'Season Pass', '2025-05-01 09:41:00'),
(2, 'Visitor 2', 'Season Pass', '2025-05-01 09:42:00'),
(3, 'Visitor 3', 'Day Pass', '2025-05-01 09:43:00'),
(4, 'Visitor 4', 'Day Pass', '2025-05-01 09:44:00'),
(5, 'Visitor 5', 'Season Pass', '2025-05-01 09:45:00'),
(6, 'Visitor 6', 'Season Pass', '2025-05-01 09:46:00'),
(7, 'Visitor 7', 'Season Pass', '2025-05-01 09:47:00'),
(8, 'Visitor 8', 'Season Pass', '2025-05-01 09:48:00'),
(9, 'Visitor 9', 'Day Pass', '2025-05-01 09:49:00'),
(10, 'Visitor 10', 'Season Pass', '2025-05-01 09:50:00'),
(11, 'Visitor 11', 'Day Pass', '2025-05-01 09:51:00'),
(12, 'Visitor 12', 'Day Pass', '2025-05-01 09:52:00'),
(13, 'Visitor 13', 'Day Pass', '2025-05-01 09:53:00'),
(14, 'Visitor 14', 'Season Pass', '2025-05-01 09:54:00'),
(15, 'Visitor 15', 'Day Pass', '2025-05-01 09:55:00'),
(16, 'Visitor 16', 'Season Pass', '2025-05-01 09:56:00'),
(17, 'Visitor 17', 'Day Pass', '2025-05-01 09:57:00'),
(18, 'Visitor 18', 'Season Pass', '2025-05-01 09:58:00'),
(19, 'Visitor 19', 'Season Pass', '2025-05-01 09:59:00'),
(20, 'Visitor 20', 'Season Pass', '2025-05-01 10:00:00'),
(21, 'Visitor 21', 'Season Pass', '2025-05-01 10:01:00'),
(22, 'Visitor 22', 'Day Pass', '2025-05-01 10:02:00'),
(23, 'Visitor 23', 'Day Pass', '2025-05-01 10:03:00'),
(24, 'Visitor 24', 'Season Pass', '2025-05-01 10:04:00'),
(25, 'Visitor 25', 'Season Pass', '2025-05-01 10:05:00'),
(26, 'Visitor 26', 'Day Pass', '2025-05-01 10:06:00'),
(27, 'Visitor 27', 'Day Pass', '2025-05-01 10:07:00'),
(28, 'Visitor 28', 'Season Pass', '2025-05-01 10:08:00'),
(29, 'Visitor 29', 'Season Pass', '2025-05-01 10:09:00'),
(30, 'Visitor 30', 'Season Pass', '2025-05-01 10:10:00'),
(31, 'Visitor 31', 'Day Pass', '2025-05-01 10:11:00'),
(32, 'Visitor 32', 'Season Pass', '2025-05-01 10:12:00'),
(33, 'Visitor 33', 'Day Pass', '2025-05-01 10:13:00'),
(34, 'Visitor 34', 'Day Pass', '2025-05-01 10:14:00'),
(35, 'Visitor 35', 'Season Pass', '2025-05-01 10:15:00'),
(36, 'Visitor 36', 'Season Pass', '2025-05-01 10:16:00'),
(37, 'Visitor 37', 'Season Pass', '2025-05-01 10:17:00'),
(38, 'Visitor 38', 'Season Pass', '2025-05-01 10:18:00'),
(39, 'Visitor 39', 'Season Pass', '2025-05-01 10:19:00'),
(40, 'Visitor 40', 'Season Pass', '2025-05-01 10:20:00'),
(41, 'Visitor 41', 'Season Pass', '2025-05-01 10:21:00'),
(42, 'Visitor 42', 'Season Pass', '2025-05-01 10:22:00'),
(43, 'Visitor 43', 'Day Pass', '2025-05-01 10:23:00'),
(44, 'Visitor 44', 'Day Pass', '2025-05-01 10:24:00'),
(45, 'Visitor 45', 'Season Pass', '2025-05-01 10:25:00'),
(46, 'Visitor 46', 'Day Pass', '2025-05-01 10:26:00'),
(47, 'Visitor 47', 'Day Pass', '2025-05-01 10:27:00'),
(48, 'Visitor 48', 'Day Pass', '2025-05-01 10:28:00'),
(49, 'Visitor 49', 'Day Pass', '2025-05-01 10:29:00'),
(50, 'Visitor 50', 'Season Pass', '2025-05-01 10:30:00'),
(51, 'Visitor 51', 'Season Pass', '2025-05-01 10:31:00'),
(52, 'Visitor 52', 'Day Pass', '2025-05-01 10:32:00'),
(53, 'Visitor 53', 'Season Pass', '2025-05-01 10:33:00'),
(54, 'Visitor 54', 'Day Pass', '2025-05-01 10:34:00'),
(55, 'Visitor 55', 'Season Pass', '2025-05-01 10:35:00'),
(56, 'Visitor 56', 'Season Pass', '2025-05-01 10:36:00'),
(57, 'Visitor 57', 'Day Pass', '2025-05-01 10:37:00'),
(58, 'Visitor 58', 'Season Pass', '2025-05-01 10:38:00'),
(59, 'Visitor 59', 'Season Pass', '2025-05-01 10:39:00'),
(60, 'Visitor 60', 'Day Pass', '2025-05-01 10:40:00'),
(61, 'Visitor 61', 'Day Pass', '2025-05-01 10:41:00'),
(62, 'Visitor 62', 'Day Pass', '2025-05-01 10:42:00'),
(63, 'Visitor 63', 'Day Pass', '2025-05-01 10:43:00'),
(64, 'Visitor 64', 'Season Pass', '2025-05-01 10:44:00'),
(65, 'Visitor 65', 'Day Pass', '2025-05-01 10:45:00'),
(66, 'Visitor 66', 'Season Pass', '2025-05-01 10:46:00'),
(67, 'Visitor 67', 'Season Pass', '2025-05-01 10:47:00'),
(68, 'Visitor 68', 'Day Pass', '2025-05-01 10:48:00'),
(69, 'Visitor 69', 'Day Pass', '2025-05-01 10:49:00'),
(70, 'Visitor 70', 'Season Pass', '2025-05-01 10:50:00'),
(71, 'Visitor 71', 'Day Pass', '2025-05-01 10:51:00'),
(72, 'Visitor 72', 'Season Pass', '2025-05-01 10:52:00'),
(73, 'Visitor 73', 'Season Pass', '2025-05-01 10:53:00'),
(74, 'Visitor 74', 'Season Pass', '2025-05-01 10:54:00'),
(75, 'Visitor 75', 'Season Pass', '2025-05-01 10:55:00'),
(76, 'Visitor 76', 'Day Pass', '2025-05-01 10:56:00'),
(77, 'Visitor 77', 'Day Pass', '2025-05-01 10:57:00'),
(78, 'Visitor 78', 'Season Pass', '2025-05-01 10:58:00'),
(79, 'Visitor 79', 'Day Pass', '2025-05-01 10:59:00'),
(80, 'Visitor 80', 'Season Pass', '2025-05-01 11:00:00'),
(81, 'Visitor 81', 'Day Pass', '2025-05-01 11:01:00'),
(82, 'Visitor 82', 'Season Pass', '2025-05-01 11:02:00'),
(83, 'Visitor 83', 'Day Pass', '2025-05-01 11:03:00'),
(84, 'Visitor 84', 'Day Pass', '2025-05-01 11:04:00'),
(85, 'Visitor 85', 'Day Pass', '2025-05-01 11:05:00'),
(86, 'Visitor 86', 'Day Pass', '2025-05-01 11:06:00'),
(87, 'Visitor 87', 'Season Pass', '2025-05-01 11:07:00'),
(88, 'Visitor 88', 'Day Pass', '2025-05-01 11:08:00'),
(89, 'Visitor 89', 'Day Pass', '2025-05-01 11:09:00'),
(90, 'Visitor 90', 'Season Pass', '2025-05-01 11:10:00'),
(91, 'Visitor 91', 'Season Pass', '2025-05-01 11:11:00'),
(92, 'Visitor 92', 'Day Pass', '2025-05-01 11:12:00'),
(93, 'Visitor 93', 'Season Pass', '2025-05-01 11:13:00'),
(94, 'Visitor 94', 'Day Pass', '2025-05-01 11:14:00'),
(95, 'Visitor 95', 'Season Pass', '2025-05-01 11:15:00'),
(96, 'Visitor 96', 'Season Pass', '2025-05-01 11:16:00'),
(97, 'Visitor 97', 'Day Pass', '2025-05-01 11:17:00'),
(98, 'Visitor 98', 'Day Pass', '2025-05-01 11:18:00'),
(99, 'Visitor 99', 'Season Pass', '2025-05-01 11:19:00'),
(100, 'Visitor 100', 'Season Pass', '2025-05-01 11:20:00');

INSERT INTO RideQueue (QueueID, VisitorID, RideID, QueueTime) VALUES
(1, 11, 83, '2025-05-01 11:21:00'),
(2, 34, 49, '2025-05-01 11:22:00'),
(3, 98, 49, '2025-05-01 11:23:00'),
(4, 3, 96, '2025-05-01 11:24:00'),
(5, 100, 84, '2025-05-01 11:25:00'),
(6, 80, 20, '2025-05-01 11:26:00'),
(7, 73, 28, '2025-05-01 11:27:00'),
(8, 78, 78, '2025-05-01 11:28:00'),
(9, 14, 75, '2025-05-01 11:29:00'),
(10, 10, 76, '2025-05-01 11:30:00'),
(11, 88, 77, '2025-05-01 11:31:00'),
(12, 85, 48, '2025-05-01 11:32:00'),
(13, 63, 14, '2025-05-01 11:33:00'),
(14, 56, 23, '2025-05-01 11:34:00'),
(15, 60, 56, '2025-05-01 11:35:00'),
(16, 12, 36, '2025-05-01 11:36:00'),
(17, 44, 4, '2025-05-01 11:37:00'),
(18, 46, 34, '2025-05-01 11:38:00'),
(19, 67, 25, '2025-05-01 11:39:00'),
(20, 89, 61, '2025-05-01 11:40:00'),
(21, 12, 38, '2025-05-01 11:41:00'),
(22, 61, 71, '2025-05-01 11:42:00'),
(23, 46, 90, '2025-05-01 11:43:00'),
(24, 16, 93, '2025-05-01 11:44:00'),
(25, 25, 28, '2025-05-01 11:45:00'),
(26, 13, 25, '2025-05-01 11:46:00'),
(27, 2, 91, '2025-05-01 11:47:00'),
(28, 71, 38, '2025-05-01 11:48:00'),
(29, 74, 37, '2025-05-01 11:49:00'),
(30, 7, 33, '2025-05-01 11:50:00'),
(31, 10, 74, '2025-05-01 11:51:00'),
(32, 73, 39, '2025-05-01 11:52:00'),
(33, 78, 77, '2025-05-01 11:53:00'),
(34, 39, 76, '2025-05-01 11:54:00'),
(35, 98, 27, '2025-05-01 11:55:00'),
(36, 21, 31, '2025-05-01 11:56:00'),
(37, 53, 58, '2025-05-01 11:57:00'),
(38, 30, 37, '2025-05-01 11:58:00'),
(39, 34, 81, '2025-05-01 11:59:00'),
(40, 70, 29, '2025-05-01 12:00:00'),
(41, 8, 22, '2025-05-01 12:01:00'),
(42, 60, 89, '2025-05-01 12:02:00'),
(43, 57, 11, '2025-05-01 12:03:00'),
(44, 78, 33, '2025-05-01 12:04:00'),
(45, 98, 87, '2025-05-01 12:05:00'),
(46, 67, 84, '2025-05-01 12:06:00'),
(47, 82, 63, '2025-05-01 12:07:00'),
(48, 42, 86, '2025-05-01 12:08:00'),
(49, 37, 85, '2025-05-01 12:09:00'),
(50, 41, 33, '2025-05-01 12:10:00'),
(51, 85, 70, '2025-05-01 12:11:00'),
(52, 80, 97, '2025-05-01 12:12:00'),
(53, 35, 71, '2025-05-01 12:13:00'),
(54, 16, 4, '2025-05-01 12:14:00'),
(55, 40, 71, '2025-05-01 12:15:00'),
(56, 15, 60, '2025-05-01 12:16:00'),
(57, 66, 91, '2025-05-01 12:17:00'),
(58, 59, 71, '2025-05-01 12:18:00'),
(59, 9, 36, '2025-05-01 12:19:00'),
(60, 1, 37, '2025-05-01 12:20:00'),
(61, 69, 62, '2025-05-01 12:21:00'),
(62, 25, 90, '2025-05-01 12:22:00'),
(63, 6, 41, '2025-05-01 12:23:00'),
(64, 64, 5, '2025-05-01 12:24:00'),
(65, 13, 68, '2025-05-01 12:25:00'),
(66, 10, 61, '2025-05-01 12:26:00'),
(67, 43, 87, '2025-05-01 12:27:00'),
(68, 70, 5, '2025-05-01 12:28:00'),
(69, 30, 96, '2025-05-01 12:29:00'),
(70, 57, 22, '2025-05-01 12:30:00'),
(71, 8, 38, '2025-05-01 12:31:00'),
(72, 68, 53, '2025-05-01 12:32:00'),
(73, 11, 79, '2025-05-01 12:33:00'),
(74, 30, 60, '2025-05-01 12:34:00'),
(75, 60, 37, '2025-05-01 12:35:00'),
(76, 45, 76, '2025-05-01 12:36:00'),
(77, 59, 39, '2025-05-01 12:37:00'),
(78, 49, 74, '2025-05-01 12:38:00'),
(79, 3, 85, '2025-05-01 12:39:00'),
(80, 78, 96, '2025-05-01 12:40:00'),
(81, 29, 82, '2025-05-01 12:41:00'),
(82, 81, 13, '2025-05-01 12:42:00'),
(83, 5, 75, '2025-05-01 12:43:00'),
(84, 42, 96, '2025-05-01 12:44:00'),
(85, 68, 65, '2025-05-01 12:45:00'),
(86, 96, 44, '2025-05-01 12:46:00'),
(87, 87, 93, '2025-05-01 12:47:00'),
(88, 2, 34, '2025-05-01 12:48:00'),
(89, 75, 49, '2025-05-01 12:49:00'),
(90, 61, 4, '2025-05-01 12:50:00'),
(91, 83, 9, '2025-05-01 12:51:00'),
(92, 15, 18, '2025-05-01 12:52:00'),
(93, 13, 31, '2025-05-01 12:53:00'),
(94, 86, 96, '2025-05-01 12:54:00'),
(95, 54, 84, '2025-05-01 12:55:00'),
(96, 89, 48, '2025-05-01 12:56:00'),
(97, 13, 88, '2025-05-01 12:57:00'),
(98, 36, 25, '2025-05-01 12:58:00'),
(99, 83, 82, '2025-05-01 12:59:00'),
(100, 17, 73, '2025-05-01 13:00:00');

INSERT INTO RideIncidents (IncidentID, RideID, IncidentType, ReportedAt) VALUES
(1, 55, 'Mechanical', '2025-05-01 13:01:00'),
(2, 42, 'Mechanical', '2025-05-01 13:02:00'),
(3, 36, 'Safety Check', '2025-05-01 13:03:00'),
(4, 70, 'Mechanical', '2025-05-01 13:04:00'),
(5, 6, 'Mechanical', '2025-05-01 13:05:00'),
(6, 31, 'Mechanical', '2025-05-01 13:06:00'),
(7, 60, 'Operator Issue', '2025-05-01 13:07:00'),
(8, 96, 'Operator Issue', '2025-05-01 13:08:00'),
(9, 4, 'Safety Check', '2025-05-01 13:09:00'),
(10, 89, 'Operator Issue', '2025-05-01 13:10:00'),
(11, 16, 'Operator Issue', '2025-05-01 13:11:00'),
(12, 9, 'Operator Issue', '2025-05-01 13:12:00'),
(13, 56, 'Safety Check', '2025-05-01 13:13:00'),
(14, 94, 'Operator Issue', '2025-05-01 13:14:00'),
(15, 94, 'Operator Issue', '2025-05-01 13:15:00'),
(16, 58, 'Mechanical', '2025-05-01 13:16:00'),
(17, 64, 'Safety Check', '2025-05-01 13:17:00'),
(18, 44, 'Safety Check', '2025-05-01 13:18:00'),
(19, 11, 'Mechanical', '2025-05-01 13:19:00'),
(20, 83, 'Operator Issue', '2025-05-01 13:20:00'),
(21, 29, 'Safety Check', '2025-05-01 13:21:00'),
(22, 68, 'Safety Check', '2025-05-01 13:22:00'),
(23, 59, 'Safety Check', '2025-05-01 13:23:00'),
(24, 25, 'Safety Check', '2025-05-01 13:24:00'),
(25, 95, 'Safety Check', '2025-05-01 13:25:00'),
(26, 38, 'Mechanical', '2025-05-01 13:26:00'),
(27, 69, 'Mechanical', '2025-05-01 13:27:00'),
(28, 90, 'Mechanical', '2025-05-01 13:28:00'),
(29, 61, 'Safety Check', '2025-05-01 13:29:00'),
(30, 62, 'Mechanical', '2025-05-01 13:30:00'),
(31, 81, 'Operator Issue', '2025-05-01 13:31:00'),
(32, 11, 'Mechanical', '2025-05-01 13:32:00'),
(33, 80, 'Mechanical', '2025-05-01 13:33:00'),
(34, 55, 'Safety Check', '2025-05-01 13:34:00'),
(35, 81, 'Mechanical', '2025-05-01 13:35:00'),
(36, 23, 'Operator Issue', '2025-05-01 13:36:00'),
(37, 89, 'Operator Issue', '2025-05-01 13:37:00'),
(38, 91, 'Safety Check', '2025-05-01 13:38:00'),
(39, 76, 'Operator Issue', '2025-05-01 13:39:00'),
(40, 83, 'Mechanical', '2025-05-01 13:40:00'),
(41, 40, 'Operator Issue', '2025-05-01 13:41:00'),
(42, 39, 'Operator Issue', '2025-05-01 13:42:00'),
(43, 77, 'Mechanical', '2025-05-01 13:43:00'),
(44, 4, 'Mechanical', '2025-05-01 13:44:00'),
(45, 35, 'Operator Issue', '2025-05-01 13:45:00'),
(46, 57, 'Safety Check', '2025-05-01 13:46:00'),
(47, 12, 'Safety Check', '2025-05-01 13:47:00'),
(48, 14, 'Mechanical', '2025-05-01 13:48:00'),
(49, 52, 'Operator Issue', '2025-05-01 13:49:00'),
(50, 42, 'Mechanical', '2025-05-01 13:50:00'),
(51, 60, 'Safety Check', '2025-05-01 13:51:00'),
(52, 64, 'Operator Issue', '2025-05-01 13:52:00'),
(53, 17, 'Safety Check', '2025-05-01 13:53:00'),
(54, 81, 'Operator Issue', '2025-05-01 13:54:00'),
(55, 2, 'Operator Issue', '2025-05-01 13:55:00'),
(56, 16, 'Operator Issue', '2025-05-01 13:56:00'),
(57, 35, 'Safety Check', '2025-05-01 13:57:00'),
(58, 19, 'Safety Check', '2025-05-01 13:58:00'),
(59, 99, 'Safety Check', '2025-05-01 13:59:00'),
(60, 93, 'Safety Check', '2025-05-01 14:00:00'),
(61, 45, 'Safety Check', '2025-05-01 14:01:00'),
(62, 31, 'Operator Issue', '2025-05-01 14:02:00'),
(63, 96, 'Safety Check', '2025-05-01 14:03:00'),
(64, 17, 'Operator Issue', '2025-05-01 14:04:00'),
(65, 59, 'Mechanical', '2025-05-01 14:05:00'),
(66, 34, 'Safety Check', '2025-05-01 14:06:00'),
(67, 69, 'Safety Check', '2025-05-01 14:07:00'),
(68, 80, 'Mechanical', '2025-05-01 14:08:00'),
(69, 12, 'Safety Check', '2025-05-01 14:09:00'),
(70, 89, 'Safety Check', '2025-05-01 14:10:00'),
(71, 46, 'Safety Check', '2025-05-01 14:11:00'),
(72, 73, 'Operator Issue', '2025-05-01 14:12:00'),
(73, 49, 'Operator Issue', '2025-05-01 14:13:00'),
(74, 82, 'Safety Check', '2025-05-01 14:14:00'),
(75, 87, 'Operator Issue', '2025-05-01 14:15:00'),
(76, 39, 'Operator Issue', '2025-05-01 14:16:00'),
(77, 26, 'Safety Check', '2025-05-01 14:17:00'),
(78, 46, 'Operator Issue', '2025-05-01 14:18:00'),
(79, 51, 'Safety Check', '2025-05-01 14:19:00'),
(80, 64, 'Safety Check', '2025-05-01 14:20:00'),
(81, 25, 'Operator Issue', '2025-05-01 14:21:00'),
(82, 81, 'Operator Issue', '2025-05-01 14:22:00'),
(83, 47, 'Operator Issue', '2025-05-01 14:23:00'),
(84, 54, 'Mechanical', '2025-05-01 14:24:00'),
(85, 35, 'Mechanical', '2025-05-01 14:25:00'),
(86, 15, 'Safety Check', '2025-05-01 14:26:00'),
(87, 87, 'Safety Check', '2025-05-01 14:27:00'),
(88, 69, 'Mechanical', '2025-05-01 14:28:00'),
(89, 82, 'Safety Check', '2025-05-01 14:29:00'),
(90, 80, 'Operator Issue', '2025-05-01 14:30:00'),
(91, 82, 'Safety Check', '2025-05-01 14:31:00'),
(92, 6, 'Mechanical', '2025-05-01 14:32:00'),
(93, 69, 'Mechanical', '2025-05-01 14:33:00'),
(94, 90, 'Operator Issue', '2025-05-01 14:34:00'),
(95, 13, 'Safety Check', '2025-05-01 14:35:00'),
(96, 28, 'Safety Check', '2025-05-01 14:36:00'),
(97, 48, 'Operator Issue', '2025-05-01 14:37:00'),
(98, 16, 'Safety Check', '2025-05-01 14:38:00'),
(99, 77, 'Mechanical', '2025-05-01 14:39:00'),
(100, 27, 'Mechanical', '2025-05-01 14:40:00');
```

### **1️⃣ Park Ride Maintenance Lookup**

**Create a non-clustered index on `ParkRides(RideType)` and `ParkRides(Status)`.**
Write a query to retrieve all **‘Roller Coaster’** rides that are currently **‘Maintenance’**.
Explain how the index helped this query.

---

### **2️⃣ Ride Queue Lookup**

**Create a non-clustered index on `RideQueue(RideID)`.**
Write a query to show all **Visitors currently queued for a specific RideID** (choose any value).
Test the query before and after creating the index.
Describe the difference.

---

### **3️⃣ Visitor Search Optimization**

The `Visitors` table has a **primary key (VisitorID)** which acts as a clustered index.
Write a query to find a Visitor by `VisitorID`.
Explain why a clustered index improves this search compared to no index.

---

### **4️⃣ Incident Report Optimization**

**Create a non-clustered index on `RideIncidents(ReportedAt)`.**
Write a query to retrieve all incidents reported in the last **24 hours**.
Explain how the index supports this query.

---

### **5️⃣ Index Impact Experiment**

First **create a non-clustered index on `RideQueue(VisitorID)`**, and test a query to show all queues for a specific VisitorID.
Then **drop the index**, rerun the query, and describe the performance difference you observe.

---

### **6️⃣ Ride Inspection Lookup**

Insert **10 new ParkRides records** with realistic `LastInspection` dates.
**Create a non-clustered index on `ParkRides(LastInspection)`** and write a query to find rides inspected before a chosen date.
Comment on how the index affects query speed.

---

### **7️⃣ Concept Comparison**

Explain in your own words:
What is the **difference between a clustered index and a non-clustered index**?
Use examples from `Visitors` (clustered) and `RideQueue` (non-clustered) to support your answer.

---

### **8️⃣ Propose an Additional Index**

Think of an extra useful index that would benefit AdventureLand’s database operations (e.g., on `Visitors(MembershipType)` or any other column).
**Write the SQL code to create this index** and justify how it would improve a specific type of query.

---
