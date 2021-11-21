# Permissions
Permissions are used to grant or deny access for different classes of users to different parts of the API.

## How permissions are determined
Permissions in REST framework are always defined as a list of permission classes.

When the permissions checks fail either a "403 Forbidden" or a "401 Unauthorized" response will be returned, according to the following rules:

* The request was successfully authenticated, but permission was denied. — An HTTP 403 Forbidden response will be returned.
* The request was not successfully authenticated, and the highest priority authentication class does not use WWW-Authenticate headers. — An HTTP 403 Forbidden response will be returned.
* The request was not successfully authenticated, and the highest priority authentication class does use WWW-Authenticate headers. — An HTTP 401 Unauthorized response, with an appropriate WWW-Authenticate header will be returned.

## Object level permissions
Object level permissions are run by REST framework's generic views when .get_object() is called. As with view level permissions, an exceptions.PermissionDenied exception will be raised if the user is not allowed to act on the given object.

> pov: With the exception of DjangoObjectPermissions, the provided permission classes in rest_framework.permissions do not implement the methods necessary to check object permissions.

## Setting the permission policy
The default permission policy may be set globally, using the DEFAULT_PERMISSION_CLASSES setting.
 For example.
```
REST_FRAMEWORK = {
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.IsAuthenticated',
    ]
}
```
If not specified, this setting defaults to allowing unrestricted access:
```
'DEFAULT_PERMISSION_CLASSES': [
   'rest_framework.permissions.AllowAny',
]
```
-----
## API Reference
* AllowAny:The AllowAny permission class will allow unrestricted access, regardless of if the request was authenticated or unauthenticated.

* IsAuthenticated:The IsAuthenticated permission class will deny permission to any unauthenticated user, and allow permission otherwise.

* IsAdminUser:The IsAdminUser permission class will deny permission to any user, unless user.is_staff is True in which case permission will be allowed.

* IsAuthenticatedOrReadOnly:The IsAuthenticatedOrReadOnly will allow authenticated users to perform any request. Requests for unauthorised users will only be permitted if the request method is one of the "safe" methods; GET, HEAD or OPTIONS.