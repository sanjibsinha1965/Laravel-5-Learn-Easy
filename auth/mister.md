# master.blade.php #

<code>

<!DOCTYPE html>
<html>
    <head>
        <title>
             @yield('title')
        </title>

        <link href='//fonts.googleapis.com/css?family=Lato:100' rel='stylesheet' typtext/css'>
              <link rel='stylesheet' href='/css/taskstyle.css'>        
    </head>
<body>
        <div class="container">
            <div class="content">
		@yield('content')
        
	
</div>
</div>
    <p class="footer">@yield('footer')</p>
</body>
</html>

</code>
