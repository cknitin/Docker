Create a Dockerfile

```
# Use the official .NET 8 SDK image as the base image for building
FROM mcr.microsoft.com/dotnet/sdk:7.0 AS build

# Set the working directory to /app
WORKDIR /app

# Copy the .csproj file and restore any dependencies
COPY *.csproj ./
RUN dotnet restore

# Copy the rest of the application code
COPY . .

# Publish the application
RUN dotnet publish -c Release -o out

# Use the official .NET 8 ASP.NET runtime image for running the application
FROM mcr.microsoft.com/dotnet/aspnet:7.0 AS runtime
WORKDIR /app
COPY --from=build /app/out ./

# Expose the port the app runs on
EXPOSE 80

# Run the application
ENTRYPOINT ["dotnet", "APITest.dll"]

```

> To Create image from Dockerfile

```
docker build -t iamcknitin/app-dot-7:latest .
```

> To Create container from image

```
docker run -it -p 5001:80 --name web-api-con iamcknitin/app-dot-7:latest /bin/bash
```

OR

run in background
```
docker run -d -p 5001:80 --name web-api-con iamcknitin/app-dot-7:latest
```

http://localhost:5001/weatherforecast

```
docker start web-api-con

docker stop web-api-con

docker attach web-api-con
```
