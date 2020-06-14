mkdir swagger_document

virtualenv env

env\Scripts\activate

(env) install django

(env) install djangorestframework

(env) install django-rest-swagger

(env) django-admin startproject swaggerDoc

(env) cd swaggerDoc


Inside swaggerDoc/settings.py add the following lines 

INSTALLED_APPS = [
    # [django core apps]
     ...
    'rest_framework',
    'rest_framework_swagger',
]
...
REST_FRAMEWORK = {
    'DEFAULT_SCHEMA_CLASS': 'rest_framework.schemas.coreapi.AutoSchema',
    # Use Django's standard `django.contrib.auth` permissions,
    # or allow read-only access for unauthenticated users.
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.DjangoModelPermissionsOrAnonReadOnly'
    ]
}
