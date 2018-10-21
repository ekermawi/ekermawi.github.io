Coding exercise
===============

1. Look at this URL: [https://journal.dumyah.com/coding-test/products](https://journal.dumyah.com/coding-test/products)
    * It is a JSON API that presents a bunch of baby products.
3. Create a very simple site that consumes this API as a client-side call and displays products in an appealing manner. A few requirements:
    * The call should be client-side and not done as an redirects
    * Filters, pagination, sorting ,and changing page limit should be done on the client-side without page refresh or redirects.
    * Brands filter is an autocomplete filter. Use [https://journal.dumyah.com/coding-test/brands](https://journal.dumyah.com/coding-test/brands) endpoint. 
    * Use HTML, CSS and jQuery (using native JS instead of jQuery is a plus)
    * The site should be responsive.  
4. Push your code to GitHub
6. In a file called `ABOUT.md`, document what you wanted to accomplish with your application. Include your thought process as you built the application. Also include what you learned in the process. Mention how much (or little) experience you have with the particular language and framework you chose.
7. Extra credit if your project is deployed in [http://heroku.com](http://heroku.com)

Then share the links for the GitHub code.  These are what we will look for in the solution:

* **Readability**: Coding style, method/variable/etc. names, encapsulation
* **Structure**: Code architecture. Try not to overarchitect your solution
* **Documentation**: Clarity of communication in your documentation. Also, the quality of your commit messages

## API Usage referance (Works for both products and brands endpoints)

    ### Filter
        
        Use `.` to access deep properties
        
        ```
        GET /products?gender=boys
        GET /products?brand.manufacturer_id=233
        ```
        
    ### Paginate
        
        Use `_page` and optionally `_limit` to paginate returned data.
        
        In the `Link` header you'll get `first`, `prev`, `next` and `last` links.
        
        
        ```
        GET /products?_page=7
        GET /products?_page=7&_limit=20
        ```
        
        _10 items are returned by default_
        
    ### Sort
        
        Add `_sort` and `_order` (ascending order by default)
        
        ```
        GET /products?_sort=views&_order=asc
        ```
       
    ### Operators
        
        Add `_gte` or `_lte` for getting a range
        
        ```
        GET /products?price_gte=10&price_lte=20
        ```
        
        Add `_ne` to exclude a value
        
        ```
        GET /products?sale_ne=false
        ```
        
        Add `_like` to filter (RegExp supported)
        
        ```
        GET /brands?name_like=chicco
        ```
        
**Additional notes:**
* Feel free to add your creative touch to the site design.
* Keep the exercise simple.  This is not something that should take more than four to eight hours of effort for someone familiar with the technologies, and maybe twice as long for someone who's never used git and heroku before.