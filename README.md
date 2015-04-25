Installation
copy all files from trunk/www to your document root
copy configuration.php-dist to configuration.php and fill out appropriate details. (There is no configuration.php file. Usually when trying to run without this Joomla will try to find the installation folder attempting to do fresh install. So, just copy configuration.php-dist to configuration.php, then edit the file and fill in the settings (like hostname, db user/password/name, physical folder structure, etc))
Create the following folders by hand. They are not added to source because the content of these folders are just temporary files that will vary from server to server:
www/cache
www/logs
www/tmp
The www/administrator has not been added under source control as the folder is very large and nothing in that folder is changed from the original distribution. Hence it is recommended to download the original Joomla distribution and simply copy the www/administrator folder from there.
For database, please use the latest database dump found at the following location:

db/
Use the latest remote file. The naming format of this file is: bdnews24_year.mo.da_remote.sql. For example:

bdnews24_2009.06.06_remote.sql
In case the date is different, please use the one with the latest date.




How to Reset the Admin Password
You may want to reset the admin password under 2 scenarios:

you have freshly installed Joomla from the source tree and your admin password should be different from the developers
you forgot your admin password and need to reset it
You need an md5 tool to generate the hashed password. For unix this should be built-in. For windows try: http://www.fourmilab.ch/md5/

Read the documentation and generate your md5 password hash. For example, the password 'secret' in md5 hash would be '5ebe2294ecd0e0f08eab7690d2a6ee69' (without the quotes).

From the phpmyadmin web interface choose your database and follow the steps below:

browse the table named jos_users
select the record ID 62 (in almost all Joomla installs) - in other words select the record where username=admin or any other username that you would like the password to be reset
replace the field value for password with the md5 generated password hash that you created above
That's it. Now you should be able to login as admin with your new username / password.


Template Positions
pagepeel
toolbar
top
breadcrumbs
search
ad_1
ad_2
ad_3
ad_4
ad_5
ad_6
advert1
advert2
user1
user2
user3
user4
user5
user6
user7
user8
user9
user10
user11
left
right_inner
right_inner1
right_inner2
right


PublishingTips  

Image Management
Images can be managed in 2 ways: via the Media manager and/or via the Article editor.

Go to Site -> Media Manager

Then click on the folder "stories". Then create a new folder or browse into an appropriate folder to upload the image.

Then to use the image in Article editor window, for example, go to Content -> Article Manager -> New

Then at the bottom of the textarea box you will see a button "Image". You can then browse to the appropriate folder where you uploaded the image to insert it in the body of the article.

Note, that through this page (Article editor) you can also upload images by clicking on the same "Image" button mentioned above.

One of the key difference between in-page image upload (Article editor) and Media Manager is, you can't create/delete folders through "Image" button in Article editor.

Breaking News
To create breaking news, start by creating a regular article.

Go to Content -> Article Manager -> New

Choose Section: Virtual
Choose Category: Breaking News
Keep the selection for radio button Frontpage: No
To have the image appear in the Breaking news box, include the following tags in the beginning and end of image tags, for example: <!--IMAGE images/stories/breaking_news/200811/sidr.jpg IMAGE-->
