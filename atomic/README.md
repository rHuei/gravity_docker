# Atomic
1. create git repository(GitHub)

2. create local git path 
```
mkdir /tmp/data
git clone -b main --single-branch https://<username>:<personal_access_token>@github.com/<username>/demoFlow.git /tmp/data/atomic
sudo chown -R 1001:1001 /tmp/data
```

3. start atomic
```
docker-compose up -d
```
