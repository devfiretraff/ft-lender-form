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