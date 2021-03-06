Version 1.0.0
* Added (minimal) documentation about how this could be used inside another jsDAV implementation
* This appears to be stable and working, so bumping to version 1.0.0

Version 0.0.5
* Added contribution guidelines and set up automated tests, fixing my own code to match
* Added logic to fetch all pages when ACD indicates there are multiple pages of results... slow because they don't use a page number so it has to be linear
* Set generic timeout for all calls of 5 minutes. Should be more than ample for transferring any file which isn't huge.
* Auto-retry when ACD rate-limits or has server-side errors
* Consolidated app to use a single temporary folder
* Implemented the /changes route from ACD - efficient updates via polling
* Standardized realPath format
* Figured out requirements for request streaming - reduces app memory footprint significantly
* pre-commit hook runs only against changes staged since last commit, ``npm test`` runs against all staged changes for all time
* Cleaned up lots of code - DRY
* Abstracted acdRequest method to accept a configuration object instead of multiple parameters
* New fs based metadata caching - combined with /changes route drastically speeds up application
* Added helper script for mounting endpoint in OSX
* Ignore and delete cache for trashed nodes

Version 0.0.4
* Added repository to package.json
* Remembered to update package.json version number
* Use jsDAV built in mime method instead of the mime module
* Baked in logging for requests as part of jsDAV debugging
* Created ``JSDAV_DEBUG`` environment variable for application
* Fixed encoding problem which caused binary files to come back mangled

Version 0.0.3
* Implemented getChild
* Abstracted the get headers -> get endpoints -> make request process into a util file
* Support for creating files
* Support for creating directories
* Support whole PUT and GET of files
* Support delete of node (moves to Trash folder in ACD)
* Support rename of node
* Support move operation
* Support copy file
* Support exists check
* Removed caching due to display not updating, but slowness means some caching will still be needed

Version 0.0.2
* Removed incorrect reference links
* Support loading as library
* Always use ``callback( err , args )`` format
* Move config beneath library load
* Preparing to share auth with jsDAV backend
* Implemented read functionality for folders and metadata
* Implemented read functionality for files along with support for partial loading via range header

Version 0.0.1
* Example config file (if you ``npm install config``)
* Investigated using aws-sdk-js, will not work for this project
* Settled on using Express for handling Amazon auth callback (would have added significant code to handle by hand)
* Figured out how to integrate jsDAV on top of ExpressJS
* Restricted use to 'localhost'
* Using [open](https://www.npmjs.com/package/open) package to load URLs, but will log them as well
* Created a rudimentary Amazon auth library for managing credentials, because aws-sdk-js won't work here
* Got application successfully authenticating against Amazon, fetching endpoints, refreshing tokens, and storing tokens until they refresh
* Moved config example to be the default and seeded with my own client\_id (but not secret)
* Removed debugMode from config as I want to use a logger later instead
* Documented config options
* Amazon Auth sends certain credentials as the hash of the URL, but we need them in the server, so signin.html makes sure either query params or hash params get passed to the /signin route as query params

Version 0.0.0
* Initialized repository
* Added LICENSE.markdown
* Added CHANGELOG.markdown
* Added CONTRIBUTING.markdown
