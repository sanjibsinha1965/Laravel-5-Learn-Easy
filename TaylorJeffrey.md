# TaylorJeffrey.php #

<code>


namespace App\Http\Controllers;

use Illuminate\Http\Request;

use App\Http\Requests;
use App\Http\Controllers\Controller;

class TaylorJeffrey extends Controller
{
    
    public function index() {
        
        $names = ['Taylor Otwell', 'Jeffrey Way'];        
        return view('taylorjeffrey.index', compact('names'));
        
    }
    
    public function show($id) {
        
        if ($id == 0){
            $name = 'Taylor Otwell';
        
            $releases = ['3.1', '3.2', '4.1', '4.2', '5.0', '5.1', '5.2.*'];

            return view('taylorjeffrey.taylor', ['id'=>$id, 'name'=> $name, 'releases'=>$releases]);
        }
        elseif ($id == 1){
            $name = '<em>Jeffrey Way</em>';   
        
        
            $laracasts = ['Installing Laravel', 'Basic Routing', 'Passing Data',
                'Migrations', 'Eloquent Outside Laravel', 'Gulp', 'Elixir'];

            return view('taylorjeffrey.jeffrey', compact('laracasts', 'id'))->with('name', $name)
                ->withWhois('Code Guru'); //it parses the variable name 
            }
        
    }
    
    public function taylor(){
        
        $name = '<em> Taylor Otwell </em>';
        
        $releases = ['3.1', '3.2', '4.1', '4.2', '5.0', '5.1', '5.2.*'];
        
        return view('taylorjeffrey.taylor', ['name'=> $name, 'releases'=>$releases]);       
    }
    public function jeffrey(){
        
        $name = '<em>Jeffrey Way</em>';   
        
        
        $laracasts = ['Installing Laravel', 'Basic Routing', 'Passing Data',
            'Migrations', 'Eloquent Outside Laravel', 'Gulp', 'Elixir'];
        
        return view('taylorjeffrey.jeffrey', compact('laracasts'))->with('name', $name)
            ->withWhois('Code Guru'); //it parses the variable name       
    }
    
    
    
}

</code>
