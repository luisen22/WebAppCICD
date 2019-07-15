FROM microsoft/dotnet:2.1-sdk AS build
#WORKDIR /app
WORKDIR /code

COPY *.csproj ./
#COPY ..
RUN dotnet restore

#COPY . ./
#RUN dotnet publish -c Release -o out
RUN dotnet publish --output /output --configuration Release

FROM microsoft/dotnet:2.1-aspnetcore-runtime As Runtime
#WORKDIR /app
#COPY --from=build /app/out .
COPY --from=build /output /app
WORKDIR /app
ENTRYPOINT ["dotnet", "WebApplicationCICD.dll"]
