# Configuring Django Settings: Best Practices


### Managing Django Settings: Issues

* Different environments: several environments: local, dev, ci, qa, staging, production, etc. Each environment can have its own specific settings

* Sensitive data: You have SECRET_KEY in each Django project. On top of this there can be DB passwords and tokens for third-party APIs like Amazon or Twitter. 

* Sharing settings between team members: You need a general approach to eliminate human error when working with the settings.

* Django settings are a Python code. This is a curse and a blessing at the same time. It gives you a lot of flexibility, but can also be a problem – instead of key-value pairs, settings.py can have a very tricky logic.

### Setting Configuration: Different Approaches
There is no built-in universal way to configure Django settings without hardcoding them.

### settings_local.py:
The basic idea of this method is to extend all environment-specific settings in the settings_local.py file, which is ignored by VCS. 

### Separate settings file for each environment:
This is an extension of the previous approach. It allows you to keep all configurations in VCS and to share default settings between developers.


### 12 Factors:
As the name suggests, the collection consists of twelve parts:
- Codebase
- Dependencies
- Config
- Backing services
- Build, release, run
- Processes
- Port binding
- Concurrency
- Disposability
- Dev/prod parity
- Logs
- Admin processes

### django-environ
Based on the above, we see that environment variables are the perfect place to store settings.

Technically it’s a merge of:
- envparse
- honcho
- dj-database-url
- dj-search-url
- dj-config-url
- django-cache-url

### Setting Structure
Instead of splitting settings by environments, you can split them by the source: Django, third- party apps (Celery, DRF, etc.), and your custom settings.

### Naming Conventions
Naming of variables is one of the most complex parts of development. So is naming of settings.
- Give meaningful names to your settings.
- Always use the prefix with the project name for your custom (project) settings.
- Write descriptions for your settings in comments.

## What is SSH
SSH, or Secure Shell, is a remote administration protocol that allows users to control and modify their remote servers over the Internet.

![](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/shell-snapshot.webp)

The SSH key command instructs your system that you want to open an encrypted Secure Shell Connection.

### Understanding Different Encryption Techniques
There are three different encryption technologies used by SSH:
1. Symmetrical encryption:
Symmetric encryption is a form of encryption where a secret key is used for both encryption and decryption of a message by both the client and the host.
![](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/symmetric-encryption-ssh-tutorial.webp)

2. Asymmetrical encryption:
Unlike symmetrical encryption, asymmetrical encryption uses two separate keys for encryption and decryption. These two keys are known as the public key and the private key.
![](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/asymmetric-encryption.webp)

3. Hashing:
One-way hashing is another form of cryptography used in Secure Shell Connections. One-way-hash functions differ from the above two forms of encryption in the sense that they are never meant to be decrypted. 
![](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/ssh-tutorial-hash.webp)