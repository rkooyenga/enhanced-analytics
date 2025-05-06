# Enhanced Analytics 
### making GA do more


** more info soon here **

To get started you need a Google tag number and to place the following into your page with any settings you want to declare:

```html
<!-- Global site tag (gtag.js) - Google Analytics -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=G-YOURTAG"></script>
    <script>
      window.dataLayer = window.dataLayer || [];
      function gtag(){dataLayer.push(arguments);}
      gtag('js', new Date());
      gtag('config', 'G-YOURTAG'); 
    </script>
<!-- Enhanced Analytics Script V2.1 -->
    <script
        src="https://path to this file /enhanced-ga.js"
        data-ga-measurement-id="G-YOURTAG"
        data-enable-auto-link-tracking="true"
        data-enable-youtube-tracking="true"       
        data-enable-html-media-tracking="true"
        data-enable-scroll-tracking="true"
        data-enable-web-vitals="true"
        data-enable-spa-tracking="true"
        data-enable-search-tracking="true"
        data-enable-vimeo-tracking="false"         
        data-enable-twitter-tracking="false"
        data-enable-form-tracking="false"   
        data-enable-pii-redaction="false"
        data-enable-adblock-detection="false"
        data-video-milestones="10,25,50,75,90,95"
        data-download-extensions="pdf,zip,doc,..."
        data-custom-dimension-map='{"site_section": "Videos Page", "user_type": "guest"}'
        defer>
    </script>
```

General guidance for Youtube, enable the jsapi and include your site as a source argument. Also it is advised to have a unique ID for the element same goes for other specialty elements. Here is a example of a working YouTube embed:
```html
<article class="entry-wrap">
      <div class="entry-content">
        <div class="embed-responsive embed-responsive-16by9">
        <iframe id="youtubePlayer_AuTKp_yULeo" width="640" height="360" src="https://www.youtube-nocookie.com/embed/AuTKp_yULeo?controls=0&amp;enablejsapi=1&amp;origin=https%3A%2F%2Frkooyenga.github.io" frameborder="0" allowfullscreen="">
        </iframe>
    </div>
<p>Born to Kill (new song)
Social Distortion
House of Blues
Anaheim, CA 01-10-2023</p>
      </div>
</article>
```

If you don't need something or aren't sure, leave it disabled not all features have been fully tested and in some cases you'll want additional libraries. FOr instance Twitter / X embeds will come with one.
```html
<!-- Enable these if you have such embeds/needs and have included their SDKs if necessary -->
        data-enable-vimeo-tracking="true"         <!-- Set to true if you use Vimeo -->
        data-enable-twitter-tracking="true"       <!-- Set to true if you use Twitter embeds -->
        data-enable-form-tracking="true"          <!-- Set to true to track basic form interactions -->


        <!-- PII and Adblock (usually false unless specifically needed) -->
        data-enable-pii-redaction="false"
        data-enable-adblock-detection="false"

        <!-- Customize these as needed -->
        data-video-milestones="10,25,50,75,90,95"
        data-download-extensions="pdf,zip,doc,..." <!-- Keep default or customize -->
        data-custom-dimension-map='{"site_section": "Videos Page", "user_type": "guest"}'
```

Ray Kooyenga for BitCurrents
