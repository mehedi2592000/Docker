

# Base Image for ASP.NET Core
FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS base
USER app
WORKDIR /app
EXPOSE 5132

# Set environment variables for HTTP binding
ENV ASPNETCORE_URLS=http://*:5132

# Build Image
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
ARG BUILD_CONFIGURATION=Release
WORKDIR /src

# Copy the project file and restore dependencies
COPY ["DockerPractice.csproj", "./"]
RUN dotnet restore "DockerPractice.csproj"

# Copy the remaining files and build the application
COPY . . 
RUN dotnet build "DockerPractice.csproj" -c $BUILD_CONFIGURATION -o /app/build

# Publish the application
FROM build AS publish
ARG BUILD_CONFIGURATION=Release
RUN dotnet publish "DockerPractice.csproj" -c $BUILD_CONFIGURATION -o /app/publish /p:UseAppHost=false

# Final Stage
FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "DockerPractice.dll"]