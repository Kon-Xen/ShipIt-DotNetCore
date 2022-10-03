# ShipIt Inventory Management

## Setup Instructions
Open the project in VSCode.
VSCode should automatically set up and install everything you'll need apart from the database connection!

### Setting up the Database.
Make sure that the directory of your Postgres, e.g. C:\Program Files\PostgreSQL\14\bin, is included in the system PATH variable. Search "environment" in Windows to find how to edit this.
Restart your code editor and then just run the command 'psql' in the terminal to check that this can run without errors.
Download the .sql file from https://techswitch.atlassian.net/wiki/spaces/0RC/pages/1510080525/Trainer+Notes+-+ShipIt and save to the ShipIt folder.
In PGAdmin, create a new user <USER> to run this project with, and a new empty database <DATABASE> owned by <USER>

Navigate to the ShipIt folder and run the following command: 
```psql -U <USER> -d postgresql://localhost:5432/<DATABASE> -f ShipIt-database-dump.sql```
Enter the password that you created for <USER> and do not worry that you cannot see the password being typed as you type it

Replicate this process for ShipItTest when required.

Then for each of the projects, add a `.env` file at the root of the project.
That file should contain a property named `POSTGRES_CONNECTION_STRING`.
The contents of the .env file should look like this:
```
POSTGRES_CONNECTION_STRING=Server=127.0.0.1;Port=5432;Database=<your_database_name>;User Id=<your_database_user>; Password=<your_database_password>;
```

If necessary, change the target framework in ShipIt.csproj to your latest version of .NET

## Running The API
Once set up, simply run dotnet run in the ShipIt directory.

## Running The Tests
To run the tests you should be able to run dotnet test in the ShipItTests directory.

## Deploying to Production
TODO
