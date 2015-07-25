# home.blade.php #

<code>
@extends('auth.master')

@section('title')
   Songs by Various Artists 
@stop

@section('content')


<h3>
    Sign Out
</h3>
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
