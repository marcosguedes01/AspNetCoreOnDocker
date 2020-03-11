### Commands
```
docker build --no-cache -t aspnet-app:v0.1 .

docker run -p 5000:80 -e LOGGING__LOGLEVEL__DEFAULT=Debug aspnet-app:v0.1
```