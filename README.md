# django-product-review

Django-review is a Django app that helps add and display reviews.

## Quick start

1. Install the needed packages

        ``pip install django-product-review django_htmx mptt``

2. Add "review" to your INSTALLED_APPS setting like this

        INSTALLED_APPS = [
            ...
            'review',
            'django_htmx',
            'widget_tweaks',
        ]
    
    AND

        MIDDLEWARE = [
            ...
            'django_htmx.middleware.HtmxMiddleware',
        ]

3. **REVIEW_PRODUCT_MODEL**
  
    Specify the model to apply review e.g

        REVIEW_PRODUCT_MODEL="inventory.Product"

4. Include the review URLconf in your project urls.py like this

        path('review/', include("review.urls", namespace="review")),
   

2. In your product detail view, pass the product to the template as *product*.

2. Add `{% load django_review %}` to the top of your product detail template

3. In the product detail template add 

        <div id="django-review">
          {% reviews product %}
        </div>
	
	to the your desired position for review

5. Run ``python manage.py migrate`` to create the review models.

7. Visit a product detail to add a review.

  