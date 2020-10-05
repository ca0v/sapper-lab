# About
This was originally created from a Vercel Temple.

I did nothing to get this scaffolding in place.  It all came from a Sapper template for Vercel.  

I notice there is no script to convert to typescript but I am starting to think maybe typescript will only be used on external dependencies that are imported into Svelte.  The need for typescript might indicate that it is time to get our of the .svelte file.  

I am still unclear as to how dependencies are loaded so I tend to want to fall back to using requirejs for explicit imports.

Vercel is not only hosts static sites but stateless methods as well.  See the `api` folder.

# Links
* [vercel](https://vercel.com) static site and serverless functions
* [sapper-lab](https://sapper-lab.vercel.app/) this site hosted on vercel