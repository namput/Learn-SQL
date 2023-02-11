# Activity 4 CS653

## Members
Aekkachai Chatpanglurlurt 6509035199 <br>
Chumphon Jangphon 6509035181 <br>
Kunanon Sukjaruen 6509035207  <br>
Ratchapol Marmongkol 6509035033 <br>
Worrapon Thongmook 6509035025 <br>


## Exercises
### 1. Create a Songs Table
[Solution](solutions/1.sql)

This table should be called `songs` and have four properties with these exact names.
1. `id`: An integer that is the primary key, and auto increments.
2. `name`: A string that cannot be null.
3. `length`: A float that represents the length of the song in minutes that cannot be null.
4. `album_id`: An integer that is a foreign key referencing the albums table that cannot be null.

After successfully creating the table copy the code from [data.sql](data.sql) into MySQL Workbench, and run it to populate all of the data for the rest of the exercises. If you do not encounter any errors, then your answer is most likely correct.

![1Fame](https://user-images.githubusercontent.com/94230186/218176814-ff5115c0-8d5c-4f27-8937-62c7e51add08.png)

### 2. Select only the Names of all the Bands
[Solution](solutions/2.sql)

Change the name of the column the data returns to `Band Name`

| Band Name         | 
|-------------------| 
| Seventh Wonder    | 
| Metallica         | 
| The Ocean         | 
| Within Temptation | 
| Death             | 
| Van Canto         | 
| Dream Theater     | 

![2Fame](https://user-images.githubusercontent.com/94230186/218176824-7a0eb8eb-bbce-4c14-b6b5-f5454597f671.png)

### 3. Select the Oldest Album
[Solution](solutions/3.sql)

Make sure to only return one result from this query, and that you are not returning any albums that do not have a release year.

| id | name                   | release_year | band_id | 
|----|------------------------|--------------|---------| 
| 5  | ...And Justice for All | 1988         | 2       | 

![3Fame](https://user-images.githubusercontent.com/94230186/218176840-2beb5b70-cdac-47ca-80c5-f64c8b3d9bf6.png)

### 4. Get all Bands that have Albums
[Solution](solutions/4.sql)

There are multiple different ways to solve this problem, but they will all involve a join.

Return the band name as `Band Name`.

| Band Name         | 
|-------------------| 
| Seventh Wonder    | 
| Metallica         | 
| The Ocean         | 
| Within Temptation | 
| Death             | 
| Van Canto         | 

![5terk](https://user-images.githubusercontent.com/94230186/218176863-24d9b410-428b-4239-986b-8da5257255db.png)

### 5. Get all Bands that have No Albums
[Solution](solutions/5.sql)

This is very similar to #4 but will require more than just a join.

Return the band name as `Band Name`.

| Band Name     | 
|---------------| 
| Dream Theater | 

![4terk](https://user-images.githubusercontent.com/94230186/218176851-d3c644a7-996c-4af5-8dcf-c53eca892b5f.png)

### 6. Get the Longest Album
[Solution](solutions/6.sql)

This problem sounds a lot like #3 but the solution is quite a bit different. I would recommend looking up the SUM aggregate function.

Return the album name as `Name`, the album release year as `Release Year`, and the album length as `Duration`.

| Name           | Release Year | Duration          | 
|----------------|--------------|-------------------| 
| Death Magnetic | 2008         | 74.76666593551636 | 

![6Go](https://user-images.githubusercontent.com/94230186/218176873-dc0b4da5-1ac2-471e-b4f1-26b92f168019.png)

### 7. Update the Release Year of the Album with no Release Year
[Solution](solutions/7.sql)

Set the release year to 1986.

You may run into an error if you try to update the release year by using `release_year IS NULL` in the WHERE statement of your UPDATE. This is because MySQL Workbench by default will not let you update a table that has a primary key without using the primary key in the UPDATE statement. This is a good thing since you almost never want to update rows without using the primary key, so to get around this error make sure to use the primary key of the row you want to update in the WHERE of the UPDATE statement.

![7Go](https://user-images.githubusercontent.com/94230186/218176881-64507193-44de-4797-9a70-0d3820c277f8.png)

### 8. Insert a record for your favorite Band and one of their Albums
[Solution](solutions/8.sql)

![8golf](https://user-images.githubusercontent.com/94230186/218176895-e4258c31-4f76-4c10-ad32-ed7da2344408.png)

### 9. Delete the Band and Album you added in #8
[Solution](solutions/9.sql)

The order of how you delete the records is important since album has a foreign key to band.

![9Golf](https://user-images.githubusercontent.com/94230186/218176904-c14cf00f-1eba-407d-ac3c-52dd7a915069.JPG)

### 10. Get the Average Length of all Songs
[Solution](solutions/10.sql)

Return the average length as `Average Song Duration`.

| Average Song Duration | 
|-----------------------| 
| 5.352472513259112     | 

![10Golf](https://user-images.githubusercontent.com/94230186/218176911-a16fdd04-337d-4f0d-8158-ded2440e516a.JPG)

### 11. Select the longest Song off each Album
[Solution](solutions/11.sql)

Return the album name as `Album`, the album release year as `Release Year`, and the longest song length as `Duration`.

| Album                       | Release Year | Duration | 
|-----------------------------|--------------|----------| 
| Tiara                       | 2018         | 9.5      | 
| The Great Escape            | 2010         | 30.2333  | 
| Mercy Falls                 | 2008         | 9.48333  | 
| Master of Puppets           | 1986         | 8.58333  | 
| ...And Justice for All      | 1988         | 9.81667  | 
| Death Magnetic              | 2008         | 9.96667  | 
| Heliocentric                | 2010         | 7.48333  | 
| Pelagial                    | 2013         | 9.28333  | 
| Anthropocentric             | 2010         | 9.4      | 
| Resist                      | 2018         | 5.85     | 
| The Unforgiving             | 2011         | 5.66667  | 
| Enter                       | 1997         | 7.25     | 
| The Sound of Perseverance   | 1998         | 8.43333  | 
| Individual Thought Patterns | 1993         | 4.81667  | 
| Human                       | 1991         | 4.65     | 
| A Storm to Come             | 2006         | 5.21667  | 
| Break the Silence           | 2011         | 6.15     | 
| Tribe of Force              | 2010         | 8.38333  | 

![11Aek](https://user-images.githubusercontent.com/94230186/218236306-f43d8299-d0e3-42d2-9883-7d2b6e17ba1b.png)

### 12. Get the number of Songs for each Band
[Solution](solutions/12.sql)

This is one of the toughest question on the list. It will require you to chain together two joins instead of just one.

Return the band name as `Band`, the number of songs as `Number of Songs`.

| Band              | Number of Songs | 
|-------------------|-----------------| 
| Seventh Wonder    | 35              | 
| Metallica         | 27              | 
| The Ocean         | 31              | 
| Within Temptation | 30              | 
| Death             | 27              | 
| Van Canto         | 32              | 

![12Aek](https://user-images.githubusercontent.com/94230186/218236308-92f81733-7ee6-4877-9265-e84ba1f7a5ab.png)
