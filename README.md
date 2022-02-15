# fix-voyager-installation-issue


https://stackoverflow.com/questions/67056520/why-cant-laravel-find-the-voyager-seeder


### First run this command
```
php artisan voyager:install --with-dummy
```
This command create all the tables and roles you need to start working with Voyager

### then run below command
```
composer dump-autoload
```
### then run your command
```
php artisan db:seed --class=VoyagerDatabaseSeeder
```
