# Download your Cloud Secure Bundle  Zip.

[🏠 Back to Reference List](../README.MD)

> The procedure is also describe in the Astra [reference documentation](https://docs.datastax.com/en/astra/docs/obtaining-database-credentials.html)

**`ASTRA DB`** is the simplest way to run Cassandra with zero operations at all - just push the button and get your cluster. No credit card required, $25.00 USD credit every month, roughly 5M writes, 30M reads, 40GB storage monthly - sufficient to run small production workloads.

### ✅ Step 1:Click the `sign-in` button to login or register.

Open a browser, navigate to Astra DB, and log in.

From your Dashboard page, select your database.

On the Overview page, select Connect.

In the Connect using a driver section, click your preferred language from the list to load language-specific instructions.

Note, though, that the bundle URL is the same for all languages.

Click Download Bundle.

If you have multiple regions, you will have the option to download a bundle for each region from the expanded Download Bundle drop-down menu.

If you’ve enabled VPC peering, you can also Download External Secure Connect Bundle for use within your VPC peering. The secure-connect-database_name.zip file downloads, which contains the security certificates and credentials for your database.

VPC peering is only available on Classic databases.

Alternatively, you can right-click the Download credentials link, copy the link source, and then use a curl command to download the secure-connect-database_name.zip file:

curl -L "<secure-connect-database_name-download-URL>" > database_name.zip
Sharing your secure connect bundle
Although teammates can access your Astra DB database, it will not display in their list of available databases under My Databases in the Astra DB console.

After you create an Astra DB database, you can grant access to other members of your team by providing them with the database credentials and connection details for your database.

Be careful when sharing connection details. Providing this information to another user grants them access to your Astra DB database and ownership capabilities, such as making modifications to the database.

For security, delete downloaded connection credentials after sending them to your teammate.

