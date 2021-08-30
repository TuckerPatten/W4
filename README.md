# W4
echo "# W4" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/TuckerPatten/W4.git
git push -u origin main
// http://localhost:55555                             // general route

// here is the refer

app.get("/", function(req,res){

  var msg=""

  msg += "<center><h1> This is the default page </h1></center>"

  msg += "use the following <br />"

  msg += " http://localhost:55555/hello <br />"

  msg += " http://localhost:55555/goodbye <br />"

  msg += " http://localhost:55555/products <br />"

  msg += " http://localhost:55555/products/2 <br />"

 

  res.send(msg);

});

 

// <<< routes = controller

// http://localhost:55555/hello                    // welcome  route

app.get("/hello", function(req,res){

  res.send("Hello ENTD261 class");

 });

 

// http://localhost:55555/goodbye                       // good bye route

app.get("/goodbye", function(req,res){

  res.send("Thank you ENTD261 class");

 });

 

// http://localhost:55555/products                       // load and display all products

app.get('/products', function(req, res) {

         res.send(JSON.stringify(products));

 });

 

// http://localhost:55555/products/2                    // load and display product id 2

app.get('/products/:id', function(req, res) {

         if (req.params.id > (products.length - 1) || req.params.id < 0) {

                 res.statusCode = 404;

                 res.end('Not Found');

         }

         res.send(JSON.stringify(products[req.params.id]));

 });
