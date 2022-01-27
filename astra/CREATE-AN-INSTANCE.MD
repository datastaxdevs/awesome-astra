# Create an Astra Instance

> The astra instance creation procedure is also described in the [reference documentation](https://docs.datastax.com/en/astra/docs/creating-your-astra-database.html)

**`ASTRA DB`** is the simplest way to run Cassandra with zero operations at all - just push the button and get your cluster. No credit card required, $25.00 USD credit every month, roughly 5M writes, 30M reads, 40GB storage monthly - sufficient to run small production workloads.

### ✅ Step 1:Click the `sign-in` button to login or register.

You can use your `Github`, `Google` accounts or register with an `email`. With the latest make sure to chose a password with minimum 8 characters, containing upper and lowercase letters, at least one number and special character.

<img src="./img/astra-login.png" />

### ✅ Step 2: Complete the creation form

<img src="./img/astra-create-db-1.png" />

- **ℹ️ Fields Description**

|Field| Description                                                                                                                                                                                                                       |
|---|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|**database name**| It does not need to be unique and not used to initialize a connection but only a label (Between 2 and 50 characters). It is recommended to have a database for each of your application. The free tier is limited to 5 databases. |
|**keyspace**| It is a logical grouping of your tables. (Between 2 and 48 characters), Please use lower cases and `snake_case`.                                                                                                                  |
|**Cloud Provider**| Use the one you like, click a cloud provider logo,  pick an Area in the list and finally pick a region. We recommend to pick one the closes to you to readuce latencies but in free tier very few difference.                     |

- ℹ️  `Create Database` button becomes enabled only when all fields are filled properly. Please use only lower cases and no space for a keyspace name.

- ℹ️  You will see your new database `pending` in the Dashboard.The status will change to `Active` when the database is ready, this will only take 2-3 minutes. You will also receive an email when it is ready.

<img src="./img/astra-create-db-pending.png" />

**👁️ Walkthrough**

<img src="./img/astra-create-db.gif" />

- ℹ️ No need to wait for the database to be in active mode to create a token
