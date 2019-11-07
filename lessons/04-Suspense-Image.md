## Suspense Image

The image takes a little bit longer to load than the rest of the data. This results in the image lagging behind.

Suspense can pre-load images into cache

`Why are we doing all of this?`
  The data that isn't the image loads first and the old image will still be present. This forces all of the data to render at the same time instead of the image lagging

`are we reinventing the browser cache here?`
  This cache that we are defining doesn't cache the actual bytes of the image but the reference to the resource that we created. We're not re-implementing the browser cache but warming it up so that other data doesn't show when images are being read into the browser cache

it wont actually switch until all the data is loaded

`Someone on react team is working on making this Image loading easier`

The browser cache exists but we don't have any control on how it works - this is allows us to bring some control to what is/isn't loaded

---

extra credit

before
 fetch data - render data → that has url in it → fetch the data with url.

when you have an api that is predictable (you know when you'll be firing a request)

e.g. /pikachu will need to load a /pikachu image

suspense will let you immediately fetch the image rather than waiting for the data to render before you fetch

`Earlier the approach was you lazy load the image but also the content. This instance forces it all to load at the same time. Would the use case be when using small images?`
  when it's a really large image - maybe you want to show some fancy fallback image or blurred image
