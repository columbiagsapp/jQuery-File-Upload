# jQuery File Upload Plugin Module for Drupal 7
This is a fork of [compujohnny's](http://drupal.org/user/369328) Drupal 7 [jQuery File Upload module](http://drupal.org/project/jquery_file_upload) 7.x-1.x-dev released on 2012-Dec-14.

His module is a great start, but is still throwing errors for some users. This is partially because is isn't up to date with blueimp's Github project jQuery File Upload that it is built on top of. For instance, blueimp's no longer uses locale.js, but this wasn't updated in the .module file. These are the types of very small updates I've made to make it work for my project.

If I was a better Drupal developer, I would probably post a patch to a Drupal forum, but I'm not, and I'm lazy, so I'm just publishing the changes that worked for me on Github in case it helps some. The /hacked drupal module/ folder is specific to a project I'm working on that uses the jQuery File Uploader with Backbone.js, and it will rarely be stable, FYI.

## Setup
* the Drupal 7 module you want to copy into /sites/all/modules is in /drupal module/
* then copy everything in the /css, /js, and /img files into the module directory (ie. /sites/all/modules/jquery_file_upload/)
* enable the module
* you **must** configure the module at /admin/config/media/jquery_file_upload to have upload quotas/maxs greater than 0 for roles you wish to be able to use the uploader
* the main.js file in the root directory is the one you want to work with, it replaces the file in /js/main.js to be Drupal 7 specific
* you'll probably want to hook into the completed() method in main.js to work with the return values:
  * name
  * size
  * url
  * thumbnail_url
  * delete_url
  * delete_type
  * files[] //an array that I added to be compliant with the done() method in jquery.fileupload-ui.js, it's redundant with url

## License
Released under the [MIT license](http://www.opensource.org/licenses/MIT).
