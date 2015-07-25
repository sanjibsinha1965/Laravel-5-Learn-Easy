# Codes of MyController.php file #

namespace App\Http\Controllers;

use Illuminate\Http\Request;
use Illuminate\Support\Facades\Auth;
use App\Http\Requests;
use App\Http\Controllers\Controller;
use DB;

class MyController extends Controller
{
    /**
     * Display a listing of the resource.
     *
     * @return Response
     */
    public function index()
    {
        $songs = DB::table('songs')->get();
        //$songs = DB::select('select * from songs');
        //$songs = DB::select('select * from songs where id = ?', [1]);
        //DB::insert('insert into songs (id, title, created_at, updated_at) values (?, ?,?, ?)', 
    //[7, 'Beautiful Boy', date('d-m-y'), date('d-m-y')]);
        DB::update('update songs set title = "I have a dream", lyrics = "Give me your hand, Let me be a man..." where id = ?', [1]);
        Auth::logout();
        var_dump($songs);     
        
    }
    /**
     * Display a listing of the resource.
     *
     * @return Response
     */
    public function about()
    {
        //
        return view('about');
        
    }

    /**
     * Show the form for creating a new resource.
     *
     * @return Response
     */
    public function create()
    {
        //
    }

    /**
     * Store a newly created resource in storage.
     *
     * @return Response
     */
    public function store()
    {
        //
    }
    public function song()
    {
        $songs = DB::table('songs')->get();
        return view('songs', compact('songs'));
        //return view('songs', compact('song'));        
        
    }

    /**
     * Display the specified resource.
     *
     * @param  int  $id
     * @return Response
     */
    public function show($id)
    {
        $songs = DB::table('songs')->find($id);
        return view('showsongs', compact('songs'));
    }

    /**
     * Show the form for editing the specified resource.
     *
     * @param  int  $id
     * @return Response
     */
    public function edit($id)
    {
        //
    }

    /**
     * Update the specified resource in storage.
     *
     * @param  int  $id
     * @return Response
     */
    public function update($id)
    {
        //
    }

    /**
     * Remove the specified resource from storage.
     *
     * @param  int  $id
     * @return Response
     */
    public function destroy($id)
    {
        //
    }
    
    public function test() {
        return view('auth.test');
    }
}
