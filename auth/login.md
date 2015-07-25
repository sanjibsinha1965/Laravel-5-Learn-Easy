# login.blade.php #

<code>
@extends('auth.master')

@section('title')
   Login Page
@stop

@section('content')
<h1>
    Sign In
</h1> 
@foreach ($errors->all() as $error)
<li>
    {{ $error }}
</li>
@endforeach
<div class="form-group">
    
    {!! Form::open(["url" => "auth/login", "method" => "POST"]) !!}   
<div class="form-group">

{!! Form::label('Name : ') !!} {!! Form::text('name')!!}
</div>
<p></p>
<div class="form-group">

{!! Form::label('Email : ') !!} {!! Form::email('email')!!}
</div>

<p></p>
<div class="form-group">

{!! Form::label('Password : ') !!} {!! Form::password('password')!!}
</div>
<p></p>

<p></p><p></p>
{!! Form::submit('Sign In') !!}

{!! Form::close() !!}
</div>

@stop

@section('footer')
   Users Registration page 
@stop

</code>
