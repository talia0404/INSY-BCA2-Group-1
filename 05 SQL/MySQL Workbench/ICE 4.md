You’ve been hired as a junior database developer at MovieMania, a new movie rental platform that stores information about customers, movies, and rental transactions. The company needs a database to keep track of their movie catalog, customers, and rental records.

Your task is to create and manage this database as per the company's evolving needs.

Create a Database called MovieManiaDB.
Create Tables:

Table: Customers

Column Name &nbsp; &nbsp;Data Type:
CustomerID &nbsp; &nbsp;INT (PK, Auto)
FirstName &nbsp; &nbsp;VARCHAR(50)
LastName &nbsp; &nbsp;VARCHAR(50)
Email &nbsp; &nbsp;VARCHAR(100)

Table: Movies

Column Name &nbsp; &nbsp;Data Type
MovieID &nbsp; &nbsp;INT (PK, Auto)
Title &nbsp; &nbsp;VARCHAR(100)
Genre &nbsp; &nbsp;VARCHAR(30)
ReleaseYear &nbsp; &nbsp;INT

3. Update a Column Name


The company wants to rename the Email column in the Customers table to ContactEmail.

4. Add a New Column


Add a PhoneNumber column (VARCHAR(20)) to the Customers table.

5. Delete a Column


The Movies table no longer needs the ReleaseYear column. Please remove it.

6. Insert Values

Insert the following sample data:

INTO Customers:

('Sarah', 'Connor', 'sarahc@email.com', '0821112233'),
('John', 'Doe', 'johnd@email.com', '0839876543');

INTOMovies:


('Inception', 'Sci-Fi'),
('The Matrix', 'Action');


7. Update Existing Values


Update Sarah Connor’s phone number to '0845556677'.

8. Delete Values


Delete the movie record with the title 'The Matrix'.


