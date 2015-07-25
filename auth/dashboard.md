# Dashboard.balde.php #

<code>

@extends('auth.master')

@section('title')
   Songs by Various Artists 
@stop

@section('content')
<h1>
    Sign In
</h1> 
<h1>
   This is Dashboard for Users
</h1>


<div class="form-group">    
    {!! Form::open(["url" => "auth/logout", "method" => "POST"]) !!}   
<p></p><p></p>
{!! Form::submit('Sign Out') !!}
{!! Form::close() !!}
</div>

@stop

@section('footer')
   Super hit Songs by Various Artists 
@stop

</code>
