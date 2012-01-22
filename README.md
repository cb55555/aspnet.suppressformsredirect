#ASP.NET Suppress Forms Authentication Redirect (cb55555 Fork)
This project combines Johnny Halife's and Phil Haack's ASP.NET Forms Authentication Suppress modules and adds some extension methods to make the suppression opt-in mechanism easier to use.

This module prevents ASP.NET Forms Authentication to redirect the user to the login page. This is helpful for AJAX, 
JSON, and all other of non Web Representation (Views/Pages) type of requests.

For more information read Phill Haack's post about this http://haacked.com/archive/2011/10/04/prevent-forms-authentication-login-page-redirect-when-you-donrsquot-want.aspx


##Installation 

Pull it from the online NuGet source, as easy as...

    install-package aspnet.suppressformsredirect


##Usage

You can use it from anywhere on your App, where you want to send a 401.

If you have a reference to the HttpContext:

    HttpContext.Current.SuppressFormsAuthRedirect();

If you only have a reference to the HttpResponseMessage, such as inside a WCF Web Api HttpOperationHandler:
    var response = new HttpResponseMessage(System.Net.HttpStatusCode.Unauthorized);
    response.SuppressFormsAuthRedirect();
    throw new HttpResponseException(response);

##Meta
Copyright (c) 2011 by Chin Bae, Johnny Halife, Phil Haack, Juan Pablo Garcia, Mauro Krikorian, Mariano Converti, Damian Martinez, Nico Bello, and Ezequiel Morito
