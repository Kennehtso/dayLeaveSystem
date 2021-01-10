# slg1f Project
	django pratice, slg1f project

# Steps to create new page
	1. run the following script under {Main Project} folder
		- python3 manage.py startapp {Page/App name}

	2 register {Page/App name} to INSTALLED_APPS Lsit, inside of the 'root/{Main Project}/settings.py'
		'{Page/App name}.apps.CatalogConfig', #This object was created for us in 'root/{Page/App name}/apps.py'
		
	3. hook up URL mapping, add the following code to 'root/{Main Project}/urls.py'
		# Use include() to add paths from the catalog application
		from django.urls import include
		urlpatterns += [
			path('{Page/App name}/', include('{Page/App name}.urls')),
		]
	4. Finally, create urls.py file inside '\{Page/App name}\'
		from django.urls import path
		from . import views

		urlpatterns = [

		]
_ _ _
# Other - Enable the serving of static files during development, add the following code to 'root/{Main Project}/urls.py'
	from django.conf import settings
	from django.conf.urls.static import static

	urlpatterns += static(settings.STATIC_URL, document_root=settings.STATIC_ROOT)

_ _ _