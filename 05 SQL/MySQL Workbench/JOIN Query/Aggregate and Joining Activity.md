### Activity: **Marvel Superheroes Headquarters Database Management**

**Scenario:**
Welcome to the **Marvel Superheroes Headquarters**! Here, the most powerful and iconic superheroes of the Marvel Universe gather to protect Earth from various threats. Your task is to create a database that helps manage superhero missions, their gadgets, and the staff that supports them.

You will create a database that tracks:
- **Superheroes** and their unique powers
- **Missions** assigned to the superheroes
- **Gadgets** used by the superheroes in their missions
- **Mission Logs** that detail mission outcomes

This database will help you keep track of superhero activities and resources to ensure the world is always protected!

---

### **Instructions:**

1. **Create a Database:**
   - Name the database: `MarvelHQDB`

2. **Create the following tables:**
   - **Heroes Table**: Information about the superheroes, their real names, powers, and ranks.
   - **Missions Table**: Information about the missions superheroes are assigned to.
   - **Gadgets Table**: Information about the gadgets used by the heroes during their missions.
   - **MissionLogs Table**: Records of completed missions and the heroes involved.

3. **Insert the following values into the tables:**

   **Heroes Table:**
   ```sql
   INSERT INTO Heroes (HeroName, RealName, Power, Rank) VALUES
   ('Iron Man', 'Tony Stark', 'Advanced technology, genius intellect', 'A'),
   ('Captain America', 'Steve Rogers', 'Super strength, enhanced agility', 'A'),
   ('Thor', 'Thor Odinson', 'God of Thunder, super strength', 'A'),
   ('Black Widow', 'Natasha Romanoff', 'Master spy, expert hand-to-hand combat', 'B'),
   ('Hulk', 'Bruce Banner', 'Super strength, regenerative healing', 'A');
   ```

   **Missions Table:**
   ```sql
   INSERT INTO Missions (MissionName, Category, DifficultyLevel) VALUES
   ('Save New York City', 'Rescue', 'High'),
   ('Defeat Thanos', 'Combat', 'High'),
   ('Recover the Tesseract', 'Espionage', 'Medium'),
   ('Protect the Shield', 'Security', 'Low'),
   ('Stop the Alien Invasion', 'Combat', 'High');
   ```

   **Gadgets Table:**
   ```sql
   INSERT INTO Gadgets (GadgetName, HeroID, GadgetType, QuantityAvailable) VALUES
   ('Iron Suit', 1, 'Armor', 3),
   ('Vibranium Shield', 2, 'Weapon', 1),
   ('Mjolnir', 3, 'Weapon', 1),
   ('Widow’s Bite', 4, 'Weapon', 4),
   ('Gamma Ray Machine', 5, 'Device', 2);
   ```

   **MissionLogs Table:**
   ```sql
   INSERT INTO MissionLogs (HeroID, MissionID, CompletionDate, MissionOutcome) VALUES
   (1, 1, '2023-03-05', 'Successful'),
   (2, 2, '2023-03-06', 'Successful'),
   (3, 3, '2023-03-07', 'Failed'),
   (4, 4, '2023-03-08', 'Successful'),
   (5, 5, '2023-03-09', 'Successful');
   ```

4. **Write the following SQL queries:**

   - **6 Medium Queries:**
     1. Calculate the total number of gadgets available for each hero.
     2. Find the average number of gadgets used by each hero.
     3. Calculate the total number of completed missions per hero.
     4. Count the number of missions completed in each category.
     5. Find the total quantity of gadgets used for a specific mission.
     6. Calculate the number of missions with a "Successful" outcome for each hero.

   - **2 Difficult Queries:**
     1. Find the hero with the highest number of missions completed and their mission details.
     2. List heroes who were assigned to missions with the highest difficulty level and their gadgets.

   - **4 Join Queries:**
     1. Use an `INNER JOIN` to get a list of missions and the heroes who participated.
     2. Use a `LEFT JOIN` to get all gadgets and the heroes who use them.
     3. Use a `RIGHT JOIN` to get a list of mission logs and the corresponding mission details.
