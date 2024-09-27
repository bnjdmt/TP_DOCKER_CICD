# Dockerfile - Worker (.NET Core)
# Build stage
FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build

WORKDIR /app

# Restaurer et compiler le projet
COPY src/Worker/Worker.csproj ./
RUN dotnet restore
COPY src/Worker ./
RUN dotnet publish -c Release -o /out Worker.csproj

# Runtime stage
FROM mcr.microsoft.com/dotnet/core/runtime:3.1

WORKDIR /app
COPY --from=build /out .

# Lancer l'application Worker
CMD ["dotnet", "worker.dll"]
