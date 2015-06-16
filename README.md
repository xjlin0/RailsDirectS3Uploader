# Rails Direct AWS S3 Uploader in the browser

Here is a working example on Rails 4.2.1 following Heroku's tutorial (updated 17 February 2015) regarding <a href="https://github.com/blueimp/jQuery-File-Upload">jQuery File Upload Plugin</a>:
"Direct to S3 Image Uploads in Rails"
https://devcenter.heroku.com/articles/direct-to-s3-image-uploads-in-rails

# Changes from the original Heroku tutorial:

1. Using <a href="https://github.com/gazay/gon">'gon' gem</a> to pass S3 variables from Ruby to JavaScript. AJAX solution can be the replacement if security is a concern.
2. Specifically using <a href="https://rubygems.org/gems/aws-sdk-v1">aws-sdk-v1' gem'</a> to avoid namespacing error.

# Working parts in files:
1. /app/controllers/users_controller.rb: The new method set the AWS service parameters in gon.
2. /app/asset/javascript/z_zjack.js: Read from gon for actual S3 uploading, get S3 stored URL and send it back to server as an attribute of the new user.

