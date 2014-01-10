This is a django app, so you'll need a working django project. I recommend reading at least the first page of this tutorial:
https://docs.djangoproject.com/en/1.6/intro/tutorial01/

But here's the 'quick' version:

* Install python (written using 2.7, but python 3 should(?) work)

* Install django (written using 1.6, try DEV if you're feeling gutsy)

* Create a django project (I called mine approvalFrame but use whatever)
	* django-admin.py startproject approvalFrame

* Setup your project's database (I used sqlite3 (included with django) for developing)
	* Edit the file 'settings.py' in the project subdirectory
	* Find the secton for DATABASES
	* Set the engine and name for whatever you're using; the comments are helpful

* Check out the approvalPolls app to the appropriate place
	* Creating a django project will create a directory with the name you choose, as well as a subdirectroy within it with that same name. Check approvalPolls out into the outer directory, so that it's a sibling of the inner directory.

* Tell django about approval polls
	* Edit the file 'settings.py' in the project subdirectory
	* Find the section for INSTALLED_APPS, and add 'approvalPolls' to the list
	* Edit the project's url.py file
	* Find urlpatterns and add 'url(r'^approvalPolls/', include('approvalPolls.urls', namespace="approvalPolls")) to the patterns list.
	* Create the database tables by running:
		* python manage.py syncdb

* Start your server
	* python manage.py runserver

* See how it looks
	* In your favorite browser, open approvalPolls/embedExample.html	

