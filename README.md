# dockerize dotnet lab

## Pré req

[dotnet sdk](https://dotnet.microsoft.com/en-us/download)

[docker](https://docs.docker.com/get-docker/)


1. Install sdk on Ubuntu 20.0.4

wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
rm packages-microsoft-prod.deb

sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-6.0

2. Install aspnet core runtime

sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-6.0

3. Install dotnet core runtime

sudo apt-get install -y dotnet-runtime-6.0

4. Create dotnet app

dotnet new console -o dotnet-lab -n DotNet.Docker

5. Run app

cd App && dotnet run

*Hello World output is expected*

```bash
Hello, World!
```

6. Publish

dotnet publish -c Release

7. Build app docker image

docker build -t dotnet-lab .

8. Run app

docker run dotnet-lab