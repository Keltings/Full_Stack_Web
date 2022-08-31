## Initialize and activate a virtualenv using:
python -m virtualenv env
source env/Scripts/activate

## Install the dependencies:
pip install -r requirements.txt

cd full_stack_web/bookshelf_app/backend
# Connect to the PostgreSQL
psql postgres
#View all databases
\l
# Create the database, create a user - `student`, grant all privileges to the student
\i setup.sql
# Exit the PostgreSQL prompt
\q

## Create tables
Once your database is created, you can create tables (bookshelf) and apply contraints
psql -f books.psql -U student -d bookshelf


export FLASK_APP=flaskr
export FLASK_ENV=development
flask run

### The command to return all of the books, which is used multiple times:

curl http://127.0.0.1:5000/books

#### To update a single book's rating:

curl http://127.0.0.1:5000/books/8 -X PATCH -H "Content-Type: application/json" -d '{"rating":"1"}'

#### To delete a single book

curl -X DELETE http://127.0.0.1:5000/books/8 

The command to return all of the books, which is used multiple times:

curl http://127.0.0.1:5000/books

#### To update a single book's rating:

curl http://127.0.0.1:5000/books/8 -X PATCH -H "Content-Type: application/json" -d '{"rating":"1"}'

#### To delete a single book

curl -X DELETE http://127.0.0.1:5000/books/8 

#### The command to use to test our book creation is:

curl -X POST -H "Content-Type: application/json" -d '{"title":"Neverwhere", "author":"Neil Gaiman", "rating":"5"}' http://127.0.0.1:5000/books   

##links for confirmations
https://github.com/udacity/cd0037-API-Development-and-Documentation-exercises/tree/master/1_Requests_Review

https://github.com/udacity/cd0037-API-Development-and-Documentation-exercises/tree/master/2_Errors_Review