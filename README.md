# Simple PHP Router

Hey! This is a simple and small php router that can handel the whole url routing for your project.
It utilizes RegExp and PHPs anonymous functions to create a lightweight and fast routing system.
The router supports dynamic path parameters, special 404 and 405 routes as well as verification of request methods like get, post, put, delete etc...
The codebase is very small and very easy to understand. So you can use it as boilerplate for a more complex router.

Take a look at the index.php file. As you can see the ```Route::add()``` method is used to add new routes to your project.
The first argument takes the path segment. You can also use RegExp in there to parse out variables. 
All matching variables will be pushed to the handler method.
The second argument will match the request method. The default method is 'get'.

## Simple example:
```
include('Route.php');

Route::add('/user/([0-9]*)/edit',function($id){
  echo 'Edit user with id '.$id.'<br/>';
},'get');

Route::run('/');
```

You will find a more complex example with a build in navigation in the index.php file.

## Use a different basepath
If your script lives in a subfolder e.g. /api/v1 set this basepath in your run method:

```Route::run('/api/v1');```

Do not forget to edit the basepath in .htaccess too if you are on apache. In order to run the test files correctly inside a basepath you should also adjust the navigation links inside the index.php.

## Something does not work?
* Dont forget to set the correct basepath as argument in your run method and in your .htaccess file.
* Enable mod_rewrite in your apache settings

## Test setup
There is a little Vagrant test setup. Just run ```vagrant up``` to spin up a Apache2 Webserver on Ubuntu. Then navigate to http://router.local after adding the machine IP to your hosts file.

## Todo
* Create demo configuration for nginx
* Create composer configuration and upload to packagist.org

## MIT License

Copyright (c) 2018 SteamPixel

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.