# Run postgres database using docker :
How to run postgres using docker ? Demo

Start a new container running PostgreSQL
We'll use docker run to start a new container from the official postgres image with the name postgres and exposing port 5432 (the PostgreSQL default).

Docker Hub is a service provided by Docker for finding and sharing container images with your team. It provides the following major features: Repositories: Push and pull container images.

https://hub.docker.com/

<img width="1300" alt="Screen Shot 2019-09-07 at 09 08 01" src="https://user-images.githubusercontent.com/30971809/64471267-b6bd6d80-d14f-11e9-9ed3-bf6132c5cf97.png">


Demo :

Step 1 :
Start the postgres database using docker :

```
$ docker-compose -f postgres.yaml up
Pulling postgres (postgres:10.3-alpine)...
10.3-alpine: Pulling from library/postgres
ff3a5c916c92: Pull complete
a503b44e1ce0: Pull complete
211706713093: Pull complete
ea28caf317dd: Pull complete
a9b37749335b: Pull complete
f7e94ebc5400: Pull complete
77dd3a51253d: Pull complete
afe61a13ac00: Pull complete
946e99ce79ff: Pull complete
Digest: sha256:b06cdddba62f1550a1c674270814e72eaa8734d95912019b4ddc288b650ad67d
Status: Downloaded newer image for postgres:10.3-alpine
Creating postgres ... done
Attaching to postgres
postgres    | The files belonging to this database system will be owned by user "postgres".
postgres    | This user must also own the server process.
postgres    |
postgres    | The database cluster will be initialized with locale "en_US.utf8".
postgres    | The default database encoding has accordingly been set to "UTF8".
postgres    | The default text search configuration will be set to "english".
postgres    |
postgres    | Data page checksums are disabled.
postgres    |
postgres    | fixing permissions on existing directory /var/lib/postgresql/data ... ok
postgres    | creating subdirectories ... ok
postgres    | selecting default max_connections ... 100
postgres    | selecting default shared_buffers ... 128MB
postgres    | selecting dynamic shared memory implementation ... posix
postgres    | creating configuration files ... ok
postgres    | running bootstrap script ... ok
postgres    | performing post-bootstrap initialization ... sh: locale: not found
postgres    | 2019-09-05 17:37:16.527 UTC [29] WARNING:  no usable system locales were found
postgres    | ok
postgres    | syncing data to disk ... ok
postgres    |
postgres    | Success. You can now start the database server using:
postgres    |
postgres    |     pg_ctl -D /var/lib/postgresql/data -l logfile start
postgres    |
postgres    |
postgres    | WARNING: enabling "trust" authentication for local connections
postgres    | You can change this by editing pg_hba.conf or using the option -A, or
postgres    | --auth-local and --auth-host, the next time you run initdb.
postgres    | waiting for server to start....2019-09-05 17:37:17.164 UTC [34] LOG:  listening on Unix socket "/var/run/postgresql/.s.PGSQL.5432"
postgres    | 2019-09-05 17:37:17.177 UTC [35] LOG:  database system was shut down at 2019-09-05 17:37:16 UTC
postgres    | 2019-09-05 17:37:17.180 UTC [34] LOG:  database system is ready to accept connections
postgres    |  done
postgres    | server started
postgres    | ALTER ROLE
postgres    |
postgres    |
postgres    | /usr/local/bin/docker-entrypoint.sh: running /docker-entrypoint-initdb.d/init.sql
postgres    | CREATE DATABASE
postgres    |
postgres    |
postgres    | waiting for server to shut down....2019-09-05 17:37:17.568 UTC [34] LOG:  received fast shutdown request
postgres    | 2019-09-05 17:37:17.571 UTC [34] LOG:  aborting any active transactions
postgres    | 2019-09-05 17:37:17.571 UTC [34] LOG:  worker process: logical replication launcher (PID 41) exited with exit code 1
postgres    | 2019-09-05 17:37:17.572 UTC [36] LOG:  shutting down
postgres    | 2019-09-05 17:37:17.583 UTC [34] LOG:  database system is shut down
postgres    |  done
postgres    | server stopped
postgres    |
postgres    | PostgreSQL init process complete; ready for start up.
postgres    |
postgres    | 2019-09-05 17:37:17.676 UTC [1] LOG:  listening on IPv4 address "0.0.0.0", port 5432
postgres    | 2019-09-05 17:37:17.676 UTC [1] LOG:  listening on IPv6 address "::", port 5432
postgres    | 2019-09-05 17:37:17.680 UTC [1] LOG:  listening on Unix socket "/var/run/postgresql/.s.PGSQL.5432"
postgres    | 2019-09-05 17:37:17.692 UTC [47] LOG:  database system was shut down at 2019-09-05 17:37:17 UTC
postgres    | 2019-09-05 17:37:17.695 UTC [1] LOG:  database system is ready to accept connections
```
Step 2 : 
Start the pgadmin - postgres client :

```
$ docker-compose -f pgadmin.yaml up
WARNING: Found orphan containers (postgres) for this project. If you removed or renamed this service in your compose file, you can run this command with the --remove-orphans flag to clean it up.
Pulling pgadmin (dpage/pgadmin4:)...
latest: Pulling from dpage/pgadmin4
e7c96db7181b: Already exists
799a5534f213: Pull complete
913b50bbe755: Pull complete
11154abc6081: Pull complete
c805e63f69fe: Pull complete
3afe03bf5f3c: Pull complete
65d57bb0cad7: Pull complete
b444394a61da: Pull complete
874797ee08cd: Pull complete
cf05aae95755: Pull complete
2979e7b3fea4: Pull complete
a5676bd9d670: Pull complete
4ae1c10da6f9: Pull complete
79e024ee70b7: Pull complete
ebb027050a5c: Pull complete
1a460aabb9f5: Pull complete
bbfd2a00629d: Pull complete
c299e51c0bc8: Pull complete
953750c925a7: Pull complete
1a2bb1c0e26f: Pull complete
14f055b208c7: Pull complete
34caff3d17cd: Pull complete
f720ecc4300c: Pull complete
3bc1b00df11c: Pull complete
6d62fac56d42: Pull complete
44bc3cf004be: Pull complete
0d127a6c9793: Pull complete
e8b16a516b48: Pull complete
33574e048e4a: Pull complete
1e030240d39e: Pull complete
3cc4cff735b1: Pull complete
b9b3f34acae6: Pull complete
9bdf9f7200f3: Pull complete
bbc7e3a6e4c8: Pull complete
5a929fbb39b2: Pull complete
Digest: sha256:59a7a17b5d1f56df43b249e933dfde9e599502c26057b87cdc64c3afd4a40241
Status: Downloaded newer image for dpage/pgadmin4:latest
Creating postgres-docker-tutorial_pgadmin_1 ... done
Attaching to postgres-docker-tutorial_pgadmin_1
pgadmin_1  | NOTE: Configuring authentication for SERVER mode.
pgadmin_1  |
pgadmin_1  | [2019-09-05 17:39:39 +0000] [1] [INFO] Starting gunicorn 19.9.0
pgadmin_1  | [2019-09-05 17:39:39 +0000] [1] [INFO] Listening at: http://[::]:80 (1)
pgadmin_1  | [2019-09-05 17:39:39 +0000] [1] [INFO] Using worker: threads
pgadmin_1  | [2019-09-05 17:39:39 +0000] [80] [INFO] Booting worker with pid: 80
```

# #CREATE TABLE interview_questions (id int, questions varchar(255));
# #INSERT INTO interview_questions (id,questions) VALUES (1, 'What is JVM');
# #select * from interview_questions;
