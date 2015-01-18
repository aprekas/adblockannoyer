#  adblockannoyer

Make adblock as annoying to your site visitors as it is to you.

**If visitors block your ad, just show them something worse than ads.**

You can see videos of the banners <a href="http://www.brittonupchurch.com/adblock-annoyer">here</a>.

##  usage

Take whichever banners you want to use. The initial ones are 300 x 250. If you want a different size, message me: tobritton@gmail.com. I'm happy to make more.

Put this in your HTML before the closing body tag:

```<script>
    // this line executes the entire code once page is loaded
    window.onload = function(){
    
    setTimeout(function() {
 
    // here we are searching for first adsense code available on page
    var ad = document.querySelector("ins.adsbygoogle");
 
    // If ad contains no innerHTML, adblocker is working
    if (ad && ad.innerHTML.replace(/\s/g, "").length == 0) {
 
    ad.style.cssText = 'display:block !important';
 
    // here you can put any html code to show as alternative
    $(".adsbygoogle").after('Your html alternative content here');
    
    }
    }, 1000);
    };
    </script>
    <script src="//ajax.googleapis.com/ajax/libs/jquery/2.1.1/jquery.min.js"></script>```

If you have more than one ad size, or want more control over where you display, replace this

```ad.style.cssText = 'display:block !important';
 
    // here you can put any html code to show as alternative
    $(".adsbygoogle").after('Your html alternative content here');```



with this

```  //here we are using a loop condition to check each ad spaces on the page
		  $(".adsbygoogle").each(function() {
			
			// Here we are checking if the ad size is 300.
			// You can use your own size. Multiple sizes can be given using && 
			
			if($(this).width()=='300'){
			ad.style.cssText = 'display:block !important';
               $(this).after('Your custom item for 300px width ad space');
			}
			// Here you may add another condition for other ad sizes
			// Same code but change ad size according to your need
			
		 });```

You can use those width-checking 'ifs' to specify what shows where.

That's it! Hope you enjoy, and send me any messages/questions.

tobritton@gmail.com