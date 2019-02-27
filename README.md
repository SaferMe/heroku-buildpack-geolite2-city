# MaxMind Build Pack (GeoLite2-City ONLY)
Ensure your application has the latest copy of **GeoLite2-City** from MaxMind.com data when deploying. Ideally, you should have a way to restart your application to make sure this build back happens often enough (if you deploy daily/weekly, you have nothing to worry about).

## How it Works
The database file(s) is saved to a Heroku cache directory that is persisted across builds. If the database file does not exist, or is older than a week, a new copy is downloaded and moved to your project before deployment. The database file is stored as `config/maxmind` from the root of your project when deployed.

## How to Use
```
heroku buildpacks:add https://github.com/SaferMe/heroku-buildpack-maxmind.git
```
