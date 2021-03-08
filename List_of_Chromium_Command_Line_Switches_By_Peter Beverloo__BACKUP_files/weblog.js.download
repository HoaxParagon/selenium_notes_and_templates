
(function ()
{
        /** the latest articles in the footer should be entirely clickable **/
        var latestArticles = document.getElementById ('latest-articles');
        if (latestArticles != null && latestArticles.getElementsByTagName)
        {
                articleList = latestArticles.getElementsByTagName ('li');
                if (articleList != null)
                {
                        for (var i = 0, j = articleList.length; i < j; i++)
                        {
                                articleList [i].onclick = function ()
                                {
                                        document.location.href = this.firstChild.href;
                                };
                                
                                articleList [i].style.cursor = 'pointer';
                        }
                }
        }
        
        /** some usability improvements for the tweet in the page's header **/
        var lastTweet = document.getElementById ('last-tweet');
        if (lastTweet != null)
        {
                /** do not open twitter when the visitor clicks on a link **/
                for (var i = 0, j = lastTweet.childNodes.length; i < j; i++)
                {
                        if (lastTweet.childNodes [i].href)
                        {
                                lastTweet.childNodes [i].onclick = function (event)
                                {
                                        event.stopPropagation ();
                                };
                        }
                }
                
                /** otherwise browse to the twitter page **/
                lastTweet.onclick = function ()
                {
                        document.location.href = this.cite;
                };
                
                lastTweet.style.cursor = 'pointer';
        }
        
        /** do we have the querySelectorAll method? **/
        if (document.querySelectorAll)
        {
                /** For legacy's sake. People should choose this for themselves. Thanks @matijs ^-^ **/
                var externalLinks = document.querySelectorAll ('a[rel="external"]');
                for (var i = 0, j = externalLinks.length; i < j; i++)
                {
                        externalLinks [i].target = "_blank";
                }
                
                /** webkit browsers support QSA. Maybe we need to handle the full-screen post **/
                var fullScreenImage = document.querySelector ('.wp-image-1880');
                if (fullScreenImage)
                {
                        fullScreenImage.style.cursor = "pointer";
                        fullScreenImage.addEventListener ('click', function ()
                        {
                                if (this.webkitRequestFullScreen)
                                {
                                        document.documentElement.webkitRequestFullScreen ();
                                }
                                else
                                {
                                        alert ('You need to install the latest WebKit Nightly on Mac OS X in order to use the full-screen API for now.');
                                }
                        
                        }, false);
                }
                
                var fullScreenLink = document.querySelector ('.fullscreen-link');
                if (fullScreenLink)
                {
                        fullScreenLink.addEventListener ('click', function ()
                        {
                                if (this.webkitRequestFullScreen)
                                {
                                        document.querySelector ('#weblog > article:first-child').webkitRequestFullScreen ();
                                }
                                else
                                {
                                        alert ('You need to install the latest WebKit Nightly on Mac OS X in order to use the full-screen API for now.');
                                }
                        
                        }, false);
                }
        }
}) ();