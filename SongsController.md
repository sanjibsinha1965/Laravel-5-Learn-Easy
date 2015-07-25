# SongsController.php #

<code>

namespace App\Http\Controllers;

use Illuminate\Http\Request;
use App\Song;
use App\Http\Requests;
use App\Http\Controllers\Controller;

class SongsController extends Controller
{
    protected $songs;
    protected $request;
    public function __construct(Song $songs, Request $request) {        
        $this->songs = $songs;
        $this->request = $request;
    }
    
    
    
    /**
     * Display a listing of the resource.
     *
     * @return Response
     */
    public function index()
    {
        
        $songs = $this->songs->get();

        return view('songs.songs', ['songs' => $songs]);
    }

    /**
     * Show the form for creating a new resource.
     *
     * @return Response
     */
    public function create()
    {
        return view('songs.songscreate');
    }

    /**
     * Store a newly created resource in storage.
     *
     * @return Response
     */
    public function store()
    {
        $this->validate($this->request, [
            'title' => 'required|unique:songs|max:255|min:2',
            'slug' => 'required||max:255|min:2',
            'lyrics' => 'required',
        ]);
        $this->songs->title = $this->request->title;
        $this->songs->slug = $this->request->slug;
        $this->songs->lyrics = $this->request->lyrics;
        $this->songs->save();
        return 'Saved';
    }
    
    /*
     * public function store(StoreSongsPostRequest $request)
    {
        $request->myrules($this->request, [
            'title' => 'required|unique:songs|max:255|min:2',
            'slug' => 'required||max:255|min:2',
            'lyrics' => 'required',
        ]);
        $this->songs->title = $this->request->title;
        $this->songs->slug = $this->request->slug;
        $this->songs->lyrics = $this->request->lyrics;
        $this->songs->save();
        return 'Saved';
    }
     * 
     */

    /**
     * Display the specified resource.
     *
     * @param  int  $id
     * @return Response
     */
    public function show($slug)
    {
        //$songs = Song::find($id);
        $songs = $this->songs->whereSlug($slug)->first();
        //$slug = $this->songs;
        return view('songs.showsongs', ['songs' => $songs]);
        //var_dump($songs);
    }

    /**
     * Show the form for editing the specified resource.
     *
     * @param  int  $id
     * @return Response
     */
    public function edit($slug)
    {
        $songs = $this->songs->whereSlug($slug)->first();
        return view('songs.editsongs', ['songs' => $songs]);
    }

    /**
     * Update the specified resource in storage.
     *
     * @param  int  $id
     * @return Response
     */
    public function update($request)
    {
        $request = $this->request;
        $songs = $this->songs->find($request->id);
        $songs->title = $request->title;
        $songs->slug = $request->slug;
        $songs->lyrics = $request->lyrics;
        $songs->save();
        return redirect('songs');
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
    
    public function test()
    {
//        $songs = $this->songs->get()->toJson();
//        return $songs;   
        //$songs = Song::findOrNew(2);
        $songs = Song::where('age', '>', 75)->firstOrFail();
        return $songs;
    }
}

</code>
