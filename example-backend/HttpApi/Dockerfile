FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base
WORKDIR /app

FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src
COPY ["HttpApi/HttpApi.csproj", "HttpApi/"]
RUN dotnet restore "HttpApi/HttpApi.csproj"
COPY . .
WORKDIR "/src/HttpApi"
RUN dotnet build "HttpApi.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "HttpApi.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
EXPOSE 80
ENTRYPOINT ["dotnet", "HttpApi.dll"]
