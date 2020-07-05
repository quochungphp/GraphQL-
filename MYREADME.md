
#Move user model to app models folder
Laravel 5 uses PSR-4 autoloader, so just move your models to another directory and change namespace in all models.

After that, run "composer dumpautoload -o" and everthing should work.

If after running the command your package will not work, try to use full namespace of User model in the package:

'user' => '\App\Entities\User',
Also, change namespace in config\auth.php (thanks @user5500750 for this):

'model' => App\Entities\User::class,