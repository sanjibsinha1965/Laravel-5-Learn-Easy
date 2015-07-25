# register.balde.php #

<code>

@extends('auth.master')

@section('title')
   Registration Page
@stop

@section('content')
<h1>
    Register
</h1> 
@foreach ($errors->all() as $error)
<li>
    {{ $error }}
</li>
@endforeach
<div class="form-group">
    
    {!! Form::open(["url" => "auth/register", "method" => "POST"]) !!}   
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
<div class="form-group">

{!! Form::label('Password Confirmation : ') !!} {!! Form::password('password_confirmation')!!}
</div>
<p></p><p></p>
{!! Form::submit('Register') !!}

{!! Form::close() !!}
</div>
@stop

@section('footer')
   Registration Page
@stop

</code>
