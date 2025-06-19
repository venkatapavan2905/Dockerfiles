# to build the application
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build

WORKDIR /app

COPY *.csproj ./

# to cache dependencies in .csproj, helps to build faster
RUN dotnet restore

COPY . .

# compiles the code to make ready for deployment, .dll file is created
RUN dotnet publish -c Release -o out

#to run the application
FROM mcr.microsoft.com/dotnet/runtime:8.0

WORKDIR /app

COPY --from=build /app/out ./

ENTRYPOINT [ "dotnet", "SampleApp.dll" ]

