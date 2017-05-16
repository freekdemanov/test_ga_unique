# test_ga_unique
test om zo veel mogelijk sessies te loggen

/* Stock GA code */

(function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
(i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
})(window,document,'script','//www.google-analytics.com/analytics.js','ga');

ga('create', 'UA-ID', 'auto');

/* If the browser_id hasn't already been set... */
if (document.cookie.indexOf('browser_uuid_set=1') == -1) {
	
	/* Generate a UUID, and assign it to the browser_id custom dimension */
	ga('set', 'dimension1', uuid.v4());
	
	/* Set a cookie so we won't override the UUID we just set */
	document.cookie = 'browser_uuid_set=1; expires=Fri, 01 Jan 2100 12:00:00 UTC; domain=.arem.us; path=/';
}

/* Assign a timestamp to the utc_millisecs custom dimension */
ga('set', 'dimension2', new Date().getTime());

/* Send a pageview */
ga('send', 'pageview');
