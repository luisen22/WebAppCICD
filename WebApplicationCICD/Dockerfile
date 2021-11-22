FROM mcr.microsoft.com/dotnet/sdk:2.1 AS build
#WORKDIR /app first commit wednesday 31th July
WORKDIR /code

COPY *.csproj ./
#COPY ..
RUN dotnet restore

COPY . ./
RUN dotnet publish -c Release -o out
#RUN dotnet publish --output /output --configuration Release

FROM mcr.microsoft.com/dotnet/aspnet:2.1 As Runtime
#WORKDIR /app
#COPY --from=build /app/out .
COPY --from=build /output /app
WORKDIR /app
ENTRYPOINT ["dotnet", "WebApplicationCICD.dll"]
#comment second
