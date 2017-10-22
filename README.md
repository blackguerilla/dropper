# dropper
Premium Linkshorter Service
 Thank you for purchasing this awesome script! This documentation will help you get familiar with this script. Please don't forget to leave this script a good rating and we would really appreciate if you can also leave us a good rating. If this script did not meet your expectation, please before leaving a low rating, contact us and hopefully, we can fix any issues you are having.

An up-to-date documenation is available online 24/7 and can be access via our portal.
Useful Links

Customer Portal

Follow us on Envato

Follow us on Twitter

Like our page on Facebook

Dedicated Support Portal
License (learn more)
Two types of license are available: Regular or Extended. If you are using this script for multiple websites, you must buy a license for each of them.

Items purchased under a Regular or Extended License may NOT be redistributed or resold "as-is" or as part of any other collection of image resources or files. You do not own the software but simply own a license to operate it therefore the author of this item has full rights on this item.
Regular License Examples (from Envato)

The Regular License could be used for the following:

    Single website (commercial, personal, or non-profit).
    Single website for a client (commercial, personal, or non-profit).
    Single intranet site project.

Extended License Examples (from Envato)

The Extended License could be used for any of the following:

    An online service where the file can be displayed on multiple users' pages.
    Part of a software package for sale.

Support
If you stumble upon an issue or if you need help you may contact via my codecanyon profile and I would be happy to help you.
Quick Guide
Installation

This script comes with a quick installer. All you have to do is to follow these simple instructions. It has been reported that the web installer may not successfully run on some servers. If that happens to you, please follow the manual installation instructions below.
Using the Web Installer

    Upload and extract "main.zip" to your server
    Point your browser to http://YOURSITE/install.php
    Follow the step by step instructions
    The script will delete the install.php after installation: Just make sure that it has been deleted.
    Login as admin using the credentials you set at step 3
    Click on "Admin" button at the top and go to settings to configure the application.

The automated installer will set up the mySQL database, create your configuration file and set up your administrator account. After this, all you have to do is to either go through this documentation to get yourself familiar with the script or you can go ahead and experiment everything on your own and come back here if you have any issues. Also don't forget that if you have any problems, you can always contact us via our codecanyon profile.
Manual Installation

In some cases the web installer may not run successfully. You will need to follow these steps to make sure that the script has been successfully installed (bolded text means input as-is).

    Upload and extract "main.zip" to your server
    Open the file includes/config_sample.php and fill in your info (remove the placeholders e.g. RUSER,RPASS,etc)
    In the same folder you will find a SQL that you will need to import to phpmyadmin
    Once imported, go to the user table and then click insert
    Fill the following columns: username=yourusename, email=youremail, admin=1, pass=SEEBELOWFORINFO, api=arandomstring, date=NOW()
    Go to the settings table and find the URL row and add your URL there e.g. http://yoursite.com (remove last slash)
    Login to the app

Important regarding Password

You must salt your password using your secret key defined in number 2 above and encode everything using MD5. Example: my password is test and my secret key is SDKJ*(udo90opaskdo90i2asd02323 so the whole thing to encod using md5 would be SDKJ*(udo90opaskdo90i2asd02323test. You can use the "Function" option in phpmyadmin to encode this.

Once everything is done simply login and the app will rencode your password using a better hashing system and it will generate your auth key.
Upgrading (click here for more info)
All upgrading instructions are detailed in "upgrade.html" located in the same folder as this file. Simply open that and follow the instructions according to the version of the script. Please note that some update may require you to replace all files while others only a couple of files. In both cases it is strongly recommended that you first backup all your existing files and download it to your computer. Click here for detailed upgrade instructions.
Configuration
Facebook Connect

You will notice that Facebook connected has now been integrated to this application. Users can now login with their Facebook and bookmark their favorite sites. To set up your app, first go to https://developers.facebook.com and set up a new app by clicking "Apps". Then click "Create New App"; Facebook will ask you to configure your app. The most important fields you must fill out are App Domains and Site URL. Following that Facebook will generate two keys for you. Go to admin settings and paste those keys. That's it. If you did everything correctly Facebook connect should work.
Twitter Connect
In this version, twitter connect has been added. Now users can login using twitter the same way they use facebook. You must enable twitter connect for it to appear and function. You can do that on the admin panel. You must register your website on Twiter.com.
Instructions

    Go to https://dev.twitter.com/apps and Login.
    Then click "Create a new application" on top right
    Fill the required fields (with a start next to it), add this to the callback field: http://YOUSITE.com/, accept the terms and conditions and click "Create your Twitter application".
    You will then be redirected to a page with your OAuth Settings
    Search & Find two keys: Consumer Key and Consumer Secret Copy these keys and paste them in admin settings
    Finally, under "settings" of your application on twitter you will see "Allow this application to be used to Sign in with Twitter". Check that and click "Update this twitter application's settings".

If you did everything correctly, Twitter OAuth should work. If it doesn't, send me an email and I will help you.
Google Connect

Google connect protocol has been changed due to restrictions from Google. For this reason you will need to set up Google connect again. Simply follow the instructions below and it should be fairly simple.

    Go https://code.google.com/apis/console and login using your Google Account
    On the left side click "Credentials"
    Then click "Create new Client ID" to open the popup
    Select "Web Application"
    Add your domain name as "http://yourdomainname.com" under Authorized Javascript Origins
    Add the URI to Google Connect under Authorized Redirect URI as "http://yourdomainname.com/user/login/google"

Google Safe Browing

Safe browsing protects your site against spam URLS. Google has a comprehensive list of spam sites. This script checks each of the url against that list and if found, it will not allow it. To enable google safe browsing, you need to grab your api key from https://developers.google.com/safe-browsing. Following that, open admin settings and add your api key to "safe_browsing". Note: To disable safe browsing, simply remove your api from config.php.
Phishtank

URLs are checked with phishtank and if they are in their database, they will not be allowed. Phishtank doesn't require an API but the use of their service will be limited.
Translation
In-App Translation
You can easily translate almost every text in this application without the hassle of editing PHP files. Just login as admin, go to settings then click on "Languages" and follow the instructions. Please note that this feature may not work on some hosts due to memory limits. In this case you will need to follow the manual instructions below.
Manual Translation
Now you can easily translate most of the text in this script. Language files are located (and have to be located) in includes/languages/<YOUR 2-LETTER LANGUAGE CODE>.php. Please note that some texts are too long to be translated this way, however you can do it another way (explained below). Once a user changes the language of the website, a cookie that includes the user's language preference will be set. If the user revisits the website, the script will automatically read the cookie and switches the language.
How Translation Works
The process of the translation is pretty easy. All texts are stored in an array and then a function is used to read and assign the proper translation of the text. If you open one of the PHP files, you will notice a lot of echo e('TEXT'). The function e is the function that reads and assigns everything. The name of the translation file is the language code of your language e.g. fr.php the code is fr for French. To use it simply, add to any link ?lang=LANGUAGECODE in this case ?lang=fr

<?php echo e('Hello')?>

Translating Texts
If you go in the includes/languages/ you will notice two files "fr.php" and "lang_sample.php". "fr.php" is an example of language file while lang_sample.php is a translation-ready file. If you want to understand how translation work, open "fr.php" and have a look at it. You will notice the following format (only the blue part must be changed): The most important things to remember are the following:

    DON'T DELETE $lang= array( and ); at the end.
    DON'T EDIT THE LEFT SIDE, if you edit it then translation will not work anymore
    DON'T FORGET DOUBLE-QUOTES BEFORE AND AFTER, if you do, you see will an error
    DON'T FORGET THIS "=>", if you do you will see an error
    And finally, DON'T FORGET THE COMMA AT THE END

Translating other Parts
If you will to translate some parts that are yet translate please do as following.

    Open the file that contains the text
    Wrap the text with this: <?php echo e('TEXT')?>
    Open your language file and then add anywhere "TEXT" => "TRANSLATED TEXT",

For pages, if for example your page name is "About", open your language file then add:

"About" => "TRANSLATION OF ABOUT",
Translating Custom Pages

If you wish to translate one of the custom pages, please follow these instructions.

    Create the original page in English (says the name is My page where the permalink will be http://YOURSITE/page/my-page)
    Create another page and put the translated name of the original one which in our example will be Ma page. If you choose to leave the slug field empty the system will create the following sluge: ma-page. DON'T leave that empty! Instead type-in manually my-page_LANGUAGECODE. So if you create a page with the following slug my-page_fr if a user decides to switch the language to French the system will attempt to get the content of that page first. If it doesn't exist, it will use the original one.
    Also make sure to NOT show the translated page in the menu but do show the original one. The system will take care of that.

Themes

The theming system has been greatly simplified to allow easy customization. It is now using bootstrap 3.1. All themes are located in the folder themes. If you open the default theme file you will see many files in that folder. Those are all the theme files you can modify. The folder named components includes some important files that you should not modify unless you know what you are doing. 
Using the editor

The script has a powerful theme editor built-in. The theme editor includes a code editor that you can use to easily change things. The code editor (ACE) is set to format only HTML and CSS. It will NOT format PHP. All php codes will be treated as text. You should not touch any PHP code unless you have the knowledge. There are some codes you can edit and these are explained below. You also have the ability to clone a theme by clicking on the clone button. You canot however delete a theme from the script. You will need to do this by deleting the folder manually. This feature was not implemented because the deletion process is very sensitive and differs from server to server.
Theme API

The new theming system offers an easy to use API that you can use to custom some stuff like widgets and features. 
Shortener Form

You can invoke the shortener form anywhere by using the following code: $this->shortener($options = array());. This function will output the shortener form in any of the theme files. You can also customize by adding some options:

$options = array('autohide' => Boolean (TRUE or FALSE), 'advanced' => Boolean (TRUE or FALSE), 'multiple' => Boolean (TRUE or FALSE));

In the code above, autohide will autohide the advanced features, advanced will either show or remove advanced features and multiple will show or remove the multiple URLs option.

Example

 $this->shortener(array('autohide' =>TRUE, 'advanced' => TRUE, 'multiple' => TRUE))
Widgets

The theming system include some widgets you can use via the theme editor. To call a widget, use $this->widgets('Widget Name',$options = array()). The list of widgets available is described below along with the options you can configure.

    Name: activities - Options: Limit (the number items to list), Refresh time in milliseconds
    Name: countries - Options: None
    Name: top_urls - Options: Limit 
    Name: tools - Options: None
    Name: social_count - Options: None
    Name: news - Options: None

Example

 $this->widgets('activities', array('limit'=>10, 'refresh' => 10000))â€‹
Menus

Menus are now built-in to the core however you can still customize them. Two menus are available: menu($options = array()) which controls the header menu and user_menu($options = array()) which controls the sidebar menu of the dashboard. Both menus are added in the file header.php in the theme folder.

Both menu accepts custom links send as an array(). See the example below:

$links = array(array('href' => 'http://google.com', 'text' => 'Google'), array('href' => 'http://apple.com', 'text' => 'Apple'));

$this->user_menu($links);
Membership

This script now offers a membership system where users can upgrade their account for a fee to use some pro features such as the custom splash page. The features that are only available to pro users are custom splash page, ability to choose the redirection type, ability to use premium aliases (set by admin), no advertisement side-wide. The fees are set via the admin panel and discounts are calculated manually. You will need to activate IPN in your PayPal account and use the following URL as the IPN receiver: http://YOURSITE.com/ipn (if you have SSL enabled make sure to use https).

Once the user clicks upgrade on top, the system will redirect to the upgrade page and will offer the user two plans: Monthly and Yearly. They will then be redirect to PayPal where they can login to pay. Once the payment has been made, the user will be redirected back and the changes will be made to the account.

The custom splash page is a feature that allows uses to create up to 5 (this can be changed) splash pages where they can use their own logo, banner, title, link to the product and their custom message. The will then be able to choose any of these 5 pages when they are shortening a URL. The maximum number of URLs can be changed in the file includes/App.class.php by changing the variable $max_splash = 5;
Expiration

The system will automatically switch the user from Pro to Free if the account has not been renewed. This will also temporarily disable all custom splash pages. Since a subscription system is currently unavailable, the user will need to renew the account every month or opt-in for the yearly plan.
Core Features
Tracking

The script offers two methods of tracking (and you can disable this): System and Google Analytics. When choosing the system method, the script will tracking users on its own and log data in the database. On the other hand, when choosing Google Analytics, the script will inject a Google Analytics code during the redirection. Please that some features are not available when using Google Analytics.
Google Analytics

Each short URL now comes with advanced statistics. Advanced stats use the powerful & free service provided by Google: Google Analytics. Using this free service will save you from storing massive amount of data in your mysql database. This scripts uses GAPI, which is a free google analytics api.

To use advanced statistics, you will need to create an account with Google and then register your site if you have not done so. You will also need to authenticate using your Google Analytics credential and then grant access to your application. Simply follow these instructions and you should be OK. You may stumble at some errors during this process, because of some settings of your server. The most common error is that Google doesn't grant access to this app to use your analytics data. If after following these instructions, you still get that error, please contact me via my codecanyon profile. But I have tested this on multiple servers and it worked fine.
Instructions

    Create an account with Google
    Register your website and copy your analytics code
    Login to this script's admin panel and add your code in the settings
    Open config.php and add your Google credentials (i.e. email and password) (and folder if you have installed in one)
    Next you will need to get your profile id. You can get that in two ways. Go to Google Analytics and click on your website (or profile). Once you get to the page where you see all charts, check the URL of that page: you should see the following: https://www.google.com/analytics/web/?hl=en#management/Profile/SOMETHINGpXXXXXXXX. The numbers following the p is your profile id. The second way is to click "Admin" then browse to your profile. You will then see several tabs click on "Profile Settings" and you will see your profile id. Copy and paste that in config.php.
    Now everything is set up correctly, but you still need to authorize your app to access your google analytics data. Open your url shortener site. Generate a short URL then go to stats page. Now here you shouldn't see any charts or maps (just blank). This is normal. Let that page open and go to https://accounts.google.com/DisplayUnlockCaptcha (make sure you are logged in with the same google account that you set up earlier. Once on that page, click "Continue" and then simply refresh your short URL stats page.
    Following these steps, the script stats should work. If it doesn't contact me and I will try to find out why.

Please note that the stats are retrieved from Google so they are not live. You may notice a lag between the number of clicks and other stats.
Caching

The script nows offers caching of data. Caching is turned off by default and can be turned on via the file includes/config.php. Data is cached using phpFastCache and is stored in the tmp folder (where cookies are stored) or in the includes/library/ depending on your server configuration. It is recommended that you turn Caching off while your site is still new to provide accurate data. However once your site reaches the 100, 000 click, you should turn it On. The caching is set to 15 minutes so the same information will be displayed for users for 15 minutes. For this reason it is not recommended to use caching while your site still new and does not have to deal with a huge dataset.
Security

This script uses some of the most advanced algorithms to keep the user account safe and your phish-free. Passwords are hashed using the phpPass library which is currently one of the best solutions. All URLs go through a series of validation as stated below:

    URL Format
    CAPTCHA Check
    Bot Check
    Keyword Blacklisting
    Domain Blacklisting
    Google Safe Check (API required: https://developers.google.com/safe-browsing/ )
    Phish-Tank Check (API not required but recommended because requests will limited: http://www.phishtank.com/developer_info.php)

Note: The password will be upgraded automatically at your first login from the old hashing algorithm. Please make sure that you use the same security key.
Multiple Domains

You can enable the multiple domains feature if you have more than one domain name. You will allow your users to choose or set a domain name by default. To add your domain names, simply fill the box in the admin section and add one domain name per line including http:// or https://. To set up your domain name, add your domain name to your server and forward all requests to your main using the following code. This following code must be added in the file .htaccess. You must the code below for each domain name.

RewriteCond %{HTTP_HOST} ^yourseconddomain\.com$ [NC]
RewriteRule ^(.*)$ http://yourfirstdomain.com/$1 [R=301,L]

