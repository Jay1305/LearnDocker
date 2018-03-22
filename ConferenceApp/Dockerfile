FROM microsoft/aspnetcore-build:2.0 AS buildAlias
WORKDIR /build
COPY . .
RUN dotnet restore
RUN dotnet publish -c Release -o output

FROM microsoft/aspnetcore:2.0
WORKDIR /app
COPY --from=buildAlias /build/output .
ENTRYPOINT ["dotnet","ConferenceApp.dll"]