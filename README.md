# Library
5 packages 
1)Config - written spring config
2)Objects - entities which used in other classes as main objects 
3)Services - classes where written all functions of objects 
4)Repositories - spring interfaces by which we can work with spring jpa
5)Controllers - Controllers used to realise services and execute their results on web application
///////////////////////////////////////////////////////////////////////////////////////////////

4 Object classes in package Objects
1)Author - Is class by which build database table which has many to many relationship with book table. has:
1. 2 constructors:
deffault constructor, set author name constructor 
2. deffault getters,setters and toString methods

2)Book - Is class by which build database table which has many to many relationship with Author table, one to many with Genres table and many to one with Users table. has:
1. 2 constructors:
deffault constructor, set title, age, date, and deffault setted "availabel" status constructor 
2. deffault getters,setters and toString methods

3)Genre - Is class by which build database table which has many to one relationship with book table. has:
1. 2 constructors:
deffault constructor, set genre constructor 
2. deffault getters,setters and toString methods

4) Users - Is class by which build database table which has one to many with Book table. has:
1. 2 constructors:
deffault constructor, set user name, surname, age constructor 
2. deffault getters,setters and toString methods
///////////////////////////////////////////////////////////////////////////////////////////////

4 Repositories - 1 repository for one object.
///////////////////////////////////////////////////////////////////////////////////////////////

4 Service classes in package Services
1)AuthorService - has 3 methods:
1. addAuthor takes author object and save it by authorRepository and returns "Author added" string.
2. ShowAuthors returns all Authors in Database.
3. ShowAuthorsBooks takes author_id by which find author in database and by book_id in author object find all his books and returns them in String format.

2)BookService - has 12 methods:
1. ShowBooks returns all Books in Database.
2. checkGenre this method takes id and used to check is any genre with given id in database if yes it returns true else returns falase. 
(Used in addGenreToBook method)
3. checkAuthor this method takes id and used to check is any Author with given id in database if yes it returns true else returns falase. 
(Used in addAuthorToBook method)
4.addBook takes Book object and save it by BookRepository and returns "Book added" string.
5.addGenreToBook takes book_id and genre_id then at first checks is any genre with given id in database if yes then add it to the book and return "Genre added to book" else return "ERROR"
6.addAuthoToBooks same as addGenreToBook
7.findBookByTitle takes title and find book which has this title then return it in book format.
8.findBooksByAge same as findBookByTitle but takes age.
9.showBookStatus takes book_id then returns String with book status.
10.showAvailableBooks returns all available books in String format.
11.showNotAvailableBooks same as showAvailableBooks but returns not available books.
12.updateBook takes book_id and book object then add changes to the given book then returns "Book updated".

3)GenreService - has 2 methods:
1. addGenre takes genre object and save it by genre Repository and returns "Genre added" string.
2. ShowGenres returns all Genres in Database.

4)UsersService - has 9 methods:
1. addUser takes Userobject and save it by UserRepository and returns "User added" string.
2. ShowUsers returns all Users in Database.
3. findUserByName takes name and find user which has this name then return it in user format.
4. findUserById same as findUserByName.
5.checkBook this method takes id and used to check is any Book with given id in database if yes it returns true else returns falase. 
(Used in addBookToUser method)
6.checkAge takes user_id and book_id then compare their ages if users bigger returns true else returns false
(Used in addBookToUser method)
7.addBookToUser takes user_id and book_id then by checkBook checkAge methods checks condtitions then if they returns true adds book to user and retruns "Book added to user" else returns "ERROR".
8.showUsersBooks takes user_id and find all his books and return them in String format.
9.updateUsers takes user_id and userobject then add changes to the given userthen returns "User updated".





