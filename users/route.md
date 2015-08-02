# routes.php

<code>

$router->get('/', function(){
    return view('welcome');
});

Route::bind('user', function ($id){
    return App\User::where('id', $id)->first();
});
$router->resource('user', 'PeopleController');

</code>
