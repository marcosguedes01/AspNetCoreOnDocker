FROM mcr.microsoft.com/dotnet/core/aspnet:3.1-buster-slim AS base
WORKDIR /app
EXPOSE 80
#EXPOSE 443

FROM mcr.microsoft.com/dotnet/core/sdk:3.1-buster AS build
WORKDIR /src
COPY ["AspNetCoreOnDocker.csproj", "AspNetCoreOnDocker/"]
RUN dotnet restore "AspNetCoreOnDocker/AspNetCoreOnDocker.csproj"
COPY . .
WORKDIR "/src/AspNetCoreOnDocker"
COPY . .
RUN dotnet build "AspNetCoreOnDocker.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "AspNetCoreOnDocker.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "AspNetCoreOnDocker.dll"]