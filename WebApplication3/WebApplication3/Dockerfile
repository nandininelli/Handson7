
FROM mcr.microsoft.com/dotnet/aspnet:3.1 AS base
WORKDIR /app
EXPOSE 80FROM mcr.microsoft.com/dotnet/sdk:3.1 AS build
WORKDIR /src
COPY WebApplication3.csproj ./
RUN dotnet restore
COPY . .
RUN dotnet build
RUN dotnet publish -c Release -o outputFROM base AS final
WORKDIR /app
COPY --from=build /src/output ./
ENTRYPOINT ["dotnet", "WebApplication3.dll"]

