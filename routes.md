# routes.php #

<code>


/*
|--------------------------------------------------------------------------
| Application Routes
|--------------------------------------------------------------------------
|
| Here is where you can register all of the routes for an application.
| It's a breeze. Simply tell Laravel the URIs it should respond to
| and give it the controller to call when that URI is requested.
|
 * Route::bind('songs', function ($slug){
    return Song::where('slug', $slug)->first();
}); 
*/
Route::group(['middleware' => 'auth'], function () {
        Route::get('home', function ()    {
            return view('auth.home');
        });

        Route::get('dashboard', function () {
            return view('auth.dashboard');
        });
        //it works
        //Route::get('test', 'MyController@test');
    });
Route::match(['get', 'post'], '/', function () {
        return view('welcome');
    });
Route::any('foo', function () {
        return 'Hello World';
    });


get('songs', 'SongsController@index');
get('songs/{slug}', 'SongsController@show');
get('songs/{songs}/edit', 'SongsController@edit');
patch('update/{id}', 'SongsController@update');
get('create', 'SongsController@create');
patch('createsongs', 'SongsController@store');
get('songsinsert', 'SongsController@test');
    
//get('/home', 'MyController@index');
get('/about', 'MyController@about');
get('/about/{id}', 'MyController@show');

get('taylorjeffrey', 'TaylorJeffrey@index');
get('taylorjeffrey/{name}', 'TaylorJeffrey@show');
get('taylorjeffrey/taylor', 'TaylorJeffrey@taylor');
get('taylorjeffrey/jeffrey', 'TaylorJeffrey@jeffrey');

Route::resource('task', 'TasksController');

    // Authentication routes...
    Route::get('auth/login', 'Auth\AuthController@getLogin');
    Route::post('auth/login', 'Auth\AuthController@postLogin');
    Route::get('auth/logout', 'Auth\AuthController@getLogout');
    Route::post('auth/logout', 'Auth\AuthController@getLogout');

    // Registration routes...
    Route::get('auth/register', 'Auth\AuthController@getRegister');
    Route::post('auth/register', 'Auth\AuthController@postRegister');
    
get('relationship', function(){

    
    $song = \App\User::find(1)->song;
    
    /*
    $songs = json_decode($song->toJson());
    return "ID = " .  $songs->{'id'}
    
    . "<br>" . "Singer ID = " .  $songs->{'singer_id'}
    . "<br>" . "User ID = " .  $songs->{'user_id'}
    . "<br>" . "Title = " .  $songs->{'title'}
    . "<br>" . "Slug = " .  $songs->{'slug'}
    . "<br>" . "Lyrics = " .  $songs->{'lyrics'};
    */
    
//    $songs = $song->attributesToArray();
//    var_dump($songs);
//    var_dump($song);
    //return $song->toJson();
    //return $song->toArray();
    //$song = new \App\Song();
    
    /*
    $songAttributes = $song->attributesToArray();    
    foreach ($songAttributes as $key => $value) {
        $songAttributes = $key . " = " . nl2br($value) . "<br>";
        echo $songAttributes;
    }
    
    */
    
    
});    
    
</code>
