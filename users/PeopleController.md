# Code of PeopleController.php

<code>

namespace App\Http\Controllers;

use Illuminate\Http\Request;
use App\User;
use App\Http\Requests;
use App\Http\Controllers\Controller;

class PeopleController extends Controller
{
    
    protected $user;

    public function __construct(User $user) {
        $this->user = $user;
    }
    
    /**
     * Display a listing of the resource.
     *
     * @return Response
     */
    public function index()
    {
        //return 'All the records of people';
        $users = $this->user->get();
        //return $users->toArray();
        return view('users.index', compact('users'));
        
    }

    /**
     * Show the form for creating a new resource.
     *
     * @return Response
     */
    public function create()
    {
        //return 'Creating People here...';
        return view('users.create');
    }

    /**
     * Store a newly created resource in storage.
     *
     * @param  Request  $request
     * @return Response
     */
    public function store(Request $request)
    {
        //return 'Storing people with ' . $request;
        //dd($request->input());
        $this->user->name = $request->get('name');
        $this->user->email = $request->get('email');
        $this->user->save();
        return redirect('user');
    }

    /**
     * Display the specified resource.
     *
     * @param  int  $id
     * @return Response
     */
    public function show($id)
    {
        //return 'People with id ' . $id;
        return view('users.show', compact('id'));
    }

    /**
     * Show the form for editing the specified resource.
     *
     * @param  int  $id
     * @return Response
     */
    public function edit($id)
    {
        //return 'Editing people with their respective ' . $id;
        return view('users.edit', compact('id'));
    }

    /**
     * Update the specified resource in storage.
     *
     * @param  Request  $request
     * @param  int  $id
     * @return Response
     */
    public function update(Request $request, $id)
    {
        //return 'Updating people with their respective ' . $id;
        //dd($request->input());
        //dd($request->get('name'));
        //dd($id->name); the id represents 'first' instead of 'second'
        $id->name = $request->get('name');
        $id->email = $request->get('email');
        $id->save();
        return redirect('user');
        
    }

    /**
     * Remove the specified resource from storage.
     *
     * @param  int  $id
     * @return Response
     */
    public function destroy($id)
    {
        return 'Deleting people records with ' . $id;
    }
}
<code>
