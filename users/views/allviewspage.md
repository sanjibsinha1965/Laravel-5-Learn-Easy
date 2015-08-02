## all view pages regarding 'CRUD' of users

# master.blade.php
<code>
<!DOCTYPE html>
<html>
    <head>
        <title>
             @yield('title')
        </title>

        <link href='//fonts.googleapis.com/css?family=Lato:100' rel='stylesheet' typtext/css'>
              <link rel='stylesheet' href='/css/style.css'>        
    </head>
<body>

<div id="container">
	<div id="body">
		@yield('content')
        </div>
	<p class="footer">@yield('footer')</p>
</div>

</body>
</html>
</code>

# index.blade.php
<code>
@extends('users.master')

@section('title')
   Users Table   
@stop

@section('content')
<h1>
    List of Users
</h1> 
@foreach($users as $user)
    
<h3>
    <a href='/user/{{ $user->id }}'>
        
        {{ $user->name }}
    </a>
    
</h3>
@endforeach

@stop

@section('footer')
<p>
    <a href="/user/create">Create New Users</a> 
   
@stop
</code>

# show.blade.php
<code>
@extends('songs.master')

@section('title')
   Detail of Users  
@stop

@section('content')
<h1>
    Detail of Users
</h1> 

<h2>
      {{ $id->name }}
</h2>

<h4>
     {{ $id->email }}
</h4>
<a href="{{ $id->id }}/edit">Edit</a>
<p>
    <a href="/user">HOME</a>
</p>
@stop

@section('footer')
  
@stop
</code>

# edit.blade.php
<code>
@extends('songs.master')

@section('title')
   Editing Users 
@stop

@section('content')
<h1>
    Editing Users
</h1> 

<div class="form-group">
    
    {!! Form::model($id, ["route" => ["user.update", $id->id], "method" => "PUT"]) !!}
    
<div class="form-group">

{!! Form::label('Name') !!} {!! Form::text('name')!!}
</div>
<p>
    
</p>
<div class="form-group">
{!! Form::label('Email') !!} {!! Form::text('email')!!}

</div>

{!! Form::submit('Update Users') !!}

{!! Form::close() !!}
</div>

@stop

@section('footer')
   Editing Users
@stop
</code>

# create.blade.php
<code>
@extends('songs.master')

@section('title')
  Create New Users
@stop

@section('content')
<h1>
    Create New Users
</h1> 
@foreach ($errors->all() as $error)
<li>
    {{ $error }}
</li>
@endforeach
<p></p><p></p>
<div class="form-group">
    
    {!! Form::open(["route" => "user.store"]) !!}
    
<div class="form-group">

{!! Form::label('Name') !!} {!! Form::text('name')!!}
</div>

<div class="form-group">
{!! Form::label('Email') !!} {!! Form::text('email')!!}

</div>

{!! Form::submit('Create New Users') !!}

{!! Form::close() !!}
</div>
@stop

@section('footer')
  Create New Users
@stop

</code>



