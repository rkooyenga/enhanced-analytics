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
