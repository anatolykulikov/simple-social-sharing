This is the simplest solution for sharing social networks and instant messengers. It does not use databases and does not display the number of reposts made.

For work you need to specify several variables:

$Link - permanent address of the page
$Title - title of the page / article
$Description - short description of the page
$Image - the path to the image (main illustration) of this page


##Facebook
```
<a href="http://www.facebook.com/sharer/sharer.php?s=100&p%5Btitle%5D=$Title&p%5Bsummary%5D=$Description&p%5Burl%5D=$Link&p%5Bimages%5D%5B0%5D=$Image" target="_blank" rel="nofollow">Share on Facebook</a>
```

##Telegram
```
<a href="https://telegram.me/share/url?url=$Link&text=$Title" target="_blank" rel="nofollow">Share on Telegram</a>
```

##vk.com
```
<a href="http://vk.com/share.php?url=$Link&title=$Title&description=$Description&image=$Image&noparse=true" target="_blank" rel="nofollow">Share on VK</a>
```

##Twitter
```
<a href="https://twitter.com/intent/tweet?original_referer=http%3A%2F%2Ffiddle.jshell.net%2F_display%2F&text=$Title&url=$Link" target="_blank" rel="nofollow">Share on Twitter</a>
```

##Mail.ru
```
<a href="http://connect.mail.ru/share?url=$Link&title=$Title&description=$Description&imageurl=$Image" target="_blank" rel="nofollow">Share on Mail.ru</a>
```

##ok.ru
```
<a href="http://www.odnoklassniki.ru/dk?st.cmd=addShare&st.s=1&st.comments=$Description&st._surl=$Link" target="_blank" rel="nofollow">Share on Odnoklassniki</a>
```

##WhatsApp (only on smartphones)
<a href="whatsapp://send?text=<?php echo urlencode('$Title'); ?>" data-action="share/whatsapp/share">Share on WhatsApp</a>

##Viber
```
<a href="viber://forward?text=$Title">Share on Viber</a>
```

##Skype
```
<a href="#" class='skype-share' data-href='$Link' data-lang='' data-text='$Title'>Share on Skype</a>
```

This javascript code is required for the operation of sharing Skype button - without it it will not work.

```javascript
!function(e,d,s){e.loadSkypeWebSdkAsync=e.loadSkypeWebSdkAsync||function(e){var t,n=d.getElementsByTagName(s)[0];d.getElementById(e.id)||((t=d.createElement(s)).id=e.id,t.src=e.scriptToLoad,t.onload=e.callback,n.parentNode.insertBefore(t,n))};e.loadSkypeWebSdkAsync({scriptToLoad:"https://swx.cdn.skype.com/shared/v/latest/skypewebsdk.js",id:"skype_web_sdk"})}(window,document,"script");
```


#Also

This code is designed to create Windows when you make sharing on social networks like Facebook and VK or messengers like Telegram. Without this code, the sharing confirmation page will open in a new tab.

```javascript
function setOnclick(t){t.setAttribute("onclick","popupWin = window.open(this.href,'contacts','toolbar=0,status=0,width=626,height=436'); popupWin.focus(); return false")}function externalLinks(){var t=document.getElementsByTagName("a");for(i=0;i<t.length;i++)t[i].getAttribute("href")&&"nofollow"==t[i].getAttribute("rel")&&setOnclick(t[i])}window.onload=externalLinks;
```
