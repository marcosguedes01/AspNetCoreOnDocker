### Commands
```
docker build --no-cache -t aspnetcoreapps/aspnetcoreondocker:latest .

docker run -p 5000:80 -e LOGGING__LOGLEVEL__DEFAULT=Debug aspnetcoreapps/aspnetcoreondocker:latest

http://localhost:5000/weatherforecast
```