🍽️ Scenario: Food Festival Races
Your job is to manage temporary race data for the current food festival season. You will use temporary tables to store and work with race records that are only relevant during the session.

🔧 Script: Create Base Tables and Data
-- Create main database

CREATE DATABASE IF NOT EXISTS FestivalRaceDB;
USE FestivalRaceDB;

-- Create permanent table: racetrack
CREATE TABLE racetrack (
    racetrack_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(250),
    location VARCHAR(250)
);

-- Create permanent table: race
CREATE TABLE race (
    race_id INT AUTO_INCREMENT PRIMARY KEY,
    racetrack_id INT,
    name VARCHAR(250),
    date DATE,
    FOREIGN KEY (racetrack_id) REFERENCES racetrack(racetrack_id)
);

-- Insert racetracks
INSERT INTO racetrack (name, location) VALUES
('Spice Speedway', 'Cape Town'),
('Pizza Plaza', 'Durban'),
('Grill Ground', 'Pretoria');

-- Insert races
INSERT INTO race (racetrack_id, name, date) VALUES
(1, 'Hot Sauce Dash', '2020-03-01'),
(2, 'Margherita Sprint', '2021-07-15'),
(3, 'Burger Blitz', '2023-09-09'),
(1, 'Chili Chase', '2019-10-01');
🔁 Temporary Table Example (Manual Definition)
CREATE TEMPORARY TABLE current_season_races (
    race_id INT AUTO_INCREMENT NOT NULL,
    racetrack_id INT NOT NULL,
    name VARCHAR(250) CHARACTER SET utf8mb4 NOT NULL,
    date DATE NOT NULL,
    PRIMARY KEY (race_id)
) ENGINE=MEMORY;
🔁 Temporary Table from Query
CREATE TEMPORARY TABLE current_season_races AS (
    SELECT *
    FROM race
    WHERE date >= '2020-01-01'
);
