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


## SQLSTATE[42000]: Syntax error or access violation: 1071 Specified key was too long; max key length is 1000 bytes 

If you are using MariaDB or an older version of MySQL, you need to place this code in your app\Providers\AppServiceProvider.php:

```
use Illuminate\Support\Facades\Schema;

public function boot()
{
    Schema::defaultStringLength(191);
}
```

## Inside config/database.php, replace this line for mysql

```
'engine' => null',
```
### with

```
'engine' => 'InnoDB ROW_FORMAT=DYNAMIC',
```

### Instead of setting a limit on your string lenght.
