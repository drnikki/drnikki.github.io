---
title: "Setting Language manually in Django 1.4"
date: 2012-10-15
---

I spent today debugging a multilingual django app that I didn't write.  The problem is that the site's language was being changed when you used the language switcher, but not if you typed in the url.  So http://example.com/fr would only _occasionally_ land you on the French version of the site. When you're using custom language codes for any reason (in our case, we were matching the client's lang codes) you're going to have to set the app's language.
<!--more-->
The relevant code:


```python
    def manual_language_function(request, lang):

        if hasattr(request, 'session'):
            request.session['django_language'] = lang
        else:
            # do something else
```

Because setting the session isn't enough, you've got to add:

```python
        translation.activate(lang)
```

And the whole thing for completeness's sake

```python
def manual_language_function(request, lang):

    if hasattr(request, 'session'):
        request.session['django_language'] = lang
        translation.activate(lang)
    else:
        # do something else
```

I lost a few hours figuring this out today, so here you go.
