# flask-minimal-blog-summernote

A minimal Flask blog with Summernote and TinyMongo

This project serves as an example of a very minimal Flask blog using TinyMongo (as an local database) and Summernote (as visual control).

This is meant not to be a serious blogging tool, but has minimal functionality to demonstrate how a larger blog could leverage
these particular tools into a bigger project.  Note that there is NO login or userid, etc. If you want that, then
I suggest using the package Flask-Login (simple implementation) or for a more comprehesive application, Flask-Security.

In addition, the app.run of Flask is blocking.  This entails finding a suitable HTTP/HTTPS server.  In the past I have used Gunicorn to deploy the app as a worker on an Nginx/Apache server or a simple Tornado wrapper can also work pretty well.  See this project if you are interested in trying that approach: https://github.com/jefmud/flask-tornado

The blog has 4 routes:
1. '/' is the index of all pages
2. '/view/\<id\>' shows a page with a particular id (this is the actual MongoDB id of the object)
3. '/edit' and '/edit/\<id\>' if no id is supplied, a new page is created.  if a valid id is presented, edit the page
4. '/delete/<id>' delete a page with a particular ID.

Flask: http://flask.pocoo.org/

A very comprehensive, robust microframework

TinyMongo: https://github.com/schapman1974/tinymongo

A PyMongo-like wrapper of tinyDB.  It is trivial to port TinyMongo to full-fledged MongoDB.

SummerNote: https://summernote.org/

Summernote is a fairly lightweight and fast WYSYWIG web control that has a Content Delivery Network implementation.
