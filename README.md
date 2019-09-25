Coding exercise
===============

1. Look at this URL: [https://staging.dumyah.com/coding-test/products](https://staging.dumyah.com/coding-test/products)
    * It is a JSON API that presents a bunch of baby products.
2. Create a very simple site that consumes this API as a server-side call and displays products in an appealing manner. A few requirements:
    * Brands filter is an autocomplete filter. Use [https://staging.dumyah.com/coding-test/brands](https://staging.dumyah.com/coding-test/brands) endpoint. 
    * The call should be server-side and not done as an AJAX call
    * The call should be dynamic (on each request) and not from a saved/cached file
    * Use PHP  language
3. Push your code to GitHub
4. In a file called `ABOUT.md`, document what you wanted to accomplish with your application. Include your thought process as you built the application. Also include what you learned in the process. Mention how much experience you have with the particular language and framework you chose.
5. Document the instructions for setting the site up in a local sandbox in your README.md file. Also document any assumptions you've made about the API or the runtime environment

Then share the links for the GitHub code.  These are what we will look for in the solution:

* **Readability**: Coding style, method/variable/etc. names, encapsulation
* **Structure**: Object design and code architecture. Try not to overarchitect your solution
* **Documentation**: Clarity of communication in your documentation. Also, the quality of your commit messages

## API Usage referance (Works for both products and brands endpoints)

### Filter
        
Use `.` to access deep properties
    
    GET /products?gender=boys
    GET /products?brand.manufacturer_id=233
        
### Paginate
        
Use `_page` and optionally `_limit` to paginate returned data.

In the `Link` header you'll get `first`, `prev`, `next` and `last` links.
    
    GET /products?_page=7
    GET /products?_page=7&_limit=20
    
_10 items are returned by default_
        
### Sort
        
Add `_sort` and `_order` (ascending order by default)
    
    GET /products?_sort=views&_order=asc
       
### Operators
        
Add `_gte` or `_lte` for getting a range
    
    GET /products?price_gte=10&price_lte=20
    
Add `_ne` to exclude a value
    
    GET /products?sale_ne=false
    
Add `_like` to filter (RegExp supported)
    
    GET /brands?name_like=chicco
    
        
**Additional notes:**
* Feel free to add your creative touch to the site design.
* Keep the exercise simple.  This is not something that should take more than four to eight hours of effort for someone familiar with the technologies, and maybe twice as long for someone who's never used git before.
