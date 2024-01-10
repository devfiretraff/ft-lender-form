To add form to lender page:
- take code from `form_with_variables.html` and insert in desired place on page
- extend head of page with styles
```html
<head>
    <link rel="stylesheet" href="assets/form.css?v=3">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">
    <script src="assets/jquery-3.6.0.min.js"></script>
</head>
```
- add script for form at the end of page
```html
<script src="assets/form.js?v=1"></script>
</body>
```

Example of full page may be found in *form-example-on-page.html*

> **Attention!** Always check *form-example-on-page.html* header in case new styles added, or some linkes changes

### For adding lender page to pre-lender:
1. Add styles to overwrite bootstrap 
```html
<style type="text/css">
    .answer > a {
        color: white !important;
        text-decoration: none !important;
    }
    img, svg {
        vertical-align: inherit !important;
    }
</style>
```
2. Wrap full body of pre-lender into div with id `pre-lender-page`
3. Wrap full body of lender into div with id `lender-page`
4. Added script to switch pages with `openForm` function
5. Search for tag *a* with `href="http://{trackingdomain}/click/` and overwrite it with next:
```html
<a class="clickToOpenForm" 
    onclick="openForm();">Postuler maintenant</a>
    <!--href="http://{trackingdomain}/click/?origin={origin}&fbpixel={lander.param:fbpixel}"   -->
    <!--onclick="fbq('track', 'InitiateCheckout');"-->
```

Example of final page
```html
<body>
    <div id="pre-lender-page">
        ...
        <a class="clickToOpenForm" onclick="openForm();">Postuler maintenant</a>
        ...
    </div>
    <div id="lender-page" style="display:none">
    </div>

    <script>
        function openForm() {
            $("#pre-lender-page").fadeOut(100);
            setTimeout(() => $("#lender-page").fadeIn(200), 100);
        }
    </script>

<body>
```