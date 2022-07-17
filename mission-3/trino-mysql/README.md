# Space Quest League Mission 3 Technical Achievement Challenge Instructions

### Running Services

First, you want to start the services. Make sure that you are in the
`space-quest-league-trino/mission-3/trino-mysql` directory. Now run the following
command:

```
docker-compose up -d
```

You should expect to see the following output (you may also have to download
the Docker images before you see the "done" message):

```
Creating trino-mysql_trino-coordinator_1 ... done
Creating trino-mysql-mysql-1             ... done
```

### Open Trino CLI

Once this is complete, you can log into the Trino coordinator node. We will
do this by using the [`exec`](https://docs.docker.com/engine/reference/commandline/exec/)
command and run the `trino` CLI executable as the command we run on that
container. Notice the container id is `trino-mysql-trino-coordinator-1` so the
command you will run is:

```
docker container exec -it trino-mysql_trino-coordinator_1 trino
```

When you start this step, you should see the `trino` cursor once the startup
is complete. It should look like this when it is done:
```
trino>
```

First, run a command to show the catalogs to see the `tpch` catalog since this is the catalog
we will query for the Technical Achievement Challenges.

```
SHOW CATALOGS;
```

You should see that the tpch catalog is available. 

### Query the tpch catalog and tiny schema 

Since Trino has to connect
to multiple databases, it supports a three-tiered containment hierarchy. Rather
than call the second tier as databases, Trino refers to this tier as schemas. So
a database in MySQL is equivalent to a schema in Trino. The third tier that 
allows Trino to distinguish between multiple underlying data sources is called a
catalog. 

You should be able
to run the following command and see that there is a `tiny` database or schema 
as it's referred to by Trino, within the `tpch` catalog.

```
SHOW SCHEMAS in tpch;
```

Run the following command to see the tables within the `tpch` catalog and `tiny` schema

```
show tables in tpch.tiny;
```

For the purpose of the Technical Achievement Challenge Sprints, we will be looking at 5 different tables:
 - customer 
 - nation
 - orders
 - region
 - supplier 

Query these tables and answer the appropriate questions.  Run an example query on the customer table and view the output

```
SELECT * FROM tpch.tiny.customer LIMIT 5;
```

The results should look like this:
```
trino> SELECT * FROM tpch.tiny.customer LIMIT 5;
 custkey |        name        |                address                 | nationkey |      phone      | acctbal | mktsegment |
---------+--------------------+----------------------------------------+-----------+-----------------+---------+------------+---------------------------
    1126 | Customer#000001126 | 8J bzLWboPqySAWPgHrl4IK4roBvb          |         8 | 18-898-994-6389 | 3905.97 | AUTOMOBILE | se carefully asymptotes. u
    1127 | Customer#000001127 | nq1w3VhKie4I3ZquEIZuz1 5CWn            |        10 | 20-830-875-6204 | 8631.35 | AUTOMOBILE | endencies. express instruc
    1128 | Customer#000001128 | 72XUL0qb4,NLmfyrtzyJlR0eP              |         0 | 10-392-200-8982 | 8123.99 | BUILDING   | odolites according to the
    1129 | Customer#000001129 | OMEqYv,hhyBAObDjIkoPL03BvuSRw02AuDPVoe |         8 | 18-313-585-9420 | 6020.02 | HOUSEHOLD  | pades affix realms. pendin
    1130 | Customer#000001130 | 60zzrBpFXjvHzyv0WObH3h8LhYbOaRID58e    |        22 | 32-503-721-8203 | 9519.36 | HOUSEHOLD  | s requests nag silently ca
(5 rows)
```

See trademark and other [legal notices](https://trino.io/legal.html).
