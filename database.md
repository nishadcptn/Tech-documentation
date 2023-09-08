# Database

## I. Basic structure.

1. We are using PostgreSQL as our Database and to support the API queries we are using [SQLAlchemy](https://www.sqlalchemy.org/) as our ORM.
2. The Database modeling is written in a file named `models.py` in each  app directory.
3. An Example of a model (Table) is as follows:

<figure><img src=".gitbook/assets/Screenshot from 2023-09-07 11-52-05.png" alt="" width="563"><figcaption></figcaption></figure>

&#x20;   **a.** Here the `id` column is considered as the primaryKey.

&#x20;   **b.** We use `uuid` as the unique identifier and the `uuid` will be used in all APIs to find the unique object.

4. The migrations are kept in `./migrations` folder.

## II. Database migration

1. For running existing migrations to database we use `flask db upgrade`
2. For creating new migration file, we can run `flask db migrate`  after updating or creating new models.

#### _Development Cycle when there is Migrations involved._

The case of Development that consists of modification of the models, The development process is mentioned below:

1. The developer who is assigned the tickets may create multiple migration files by using the command `flask db migrate`
2. These migration files **should not be committed into git**, only the model changes should be committed.
3. The developer will rebase the target branch and Once the PR is approved,then they would create one single migration file in the branch, commit and should be merged with high priority.
4.

