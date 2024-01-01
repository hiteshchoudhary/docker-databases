# Start local Redis and Redis Insight client

### When `docker-compose.yml` is in the root folder

```bash
docker-compose up
```

### When `docker-compose.yml` is in the nested folders

```bash
docker-compose -f ./redis/docker-compose.yml up
```

# Access Redis Insight dashboard

- Go to `http://localhost:8001` to access the Redis Insight.
- Accept the necessary T&Cs.
- Click on **"I already have a database"**
- Click on **"Connect to Redis database"**
- Enter the following configuration and click on **"Add Redis Database"**:

<img src="https://wajeshubham-portfolio.s3.ap-south-1.amazonaws.com/redis-config.png"/>

- We have used `redis` as a `Host` because the `Redis Insight` container is also running on the docker, in the same network as the `redis` container.

- So, to access a services in the same network, we use their name as the `Host`. So, that's why we used `redis` (name of the service for redis container in the `docker-compose.yml` file)

- You are connected to the Redis database!

# `Set` and `Get` a key in the Redis

Now that you are connected to the Redis database through Redis Insight, let's set and get a key.

After connecting to the redis. Refer to the following video as a guide:

[![Redis through Redis insight](https://img.youtube.com/vi/Z4pAv2-NVSI/0.jpg)](https://www.youtube.com/watch?v=Z4pAv2-NVSI)

Now, you have a running redis instance!
