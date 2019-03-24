#### Why would you consider a Scripting Language as JavaScript as your Backend Platform?
Node.js is a lean, fast, cross-platform JavaScript runtime environment that is useful for both servers and desktop applications. 
It is used by big companies as LinkedIn and Uber. 
And of course, smaller tech startups have built their platforms using Node.js and 
increasingly more enterprise companies are migrating their platforms from legacy code to the more robust and streamlined Node.

#### Explain Pros & Cons in using Node.js + Express to implement your Backend compared to a strategy using, for example, Java/JAX-RS/Tomcat

#### Pros:

Asynchronous event driven IO helps concurrent request handling.
Share the same piece of code with both server and client side.
npm, the Node packaged modules has already become huge, and still growing.
You can stream big files.

#### Cons:

Node.js doesn’t provide scalability. One CPU is not going to be enough; the platform provides no ability to scale out to take advantage of the multiple cores commonly present in today’s server-class hardware.
Every time using a callback end up with tons of nested callbacks.
Node.js is not suited for CPU-intensive tasks. It is suited for I/O stuff only (like web servers).

#### Explain briefly how to deploy a Node/Express application including how to solve the following deployment problems:
- Ensure that you Node-process restarts after a (potential) exception that closed the application
Express' own docs recommend using a process manager. (https://expressjs.com/en/advanced/pm.html)

- Ensure that you Node-process restarts after a server (Ubuntu) restart
Process manager can handle this.

- Ensure that you can run “many” node-applications on a single droplet on the same port (80)
This can be done using NGINX. (https://docs.nginx.com/nginx/admin-guide/web-server/reverse-proxy/)

#### Explain, generally, what is meant by a NoSQL database.
-A NoSQL database provides storage and retrieval of data that is modeled in means other than the tabular relations used in relational databases. 
-NoSQL databases are increasingly used in big data and real-time web applications.

#### Explain Pros & Cons in using a NoSQL database like MongoDB as your data store, compared to a traditional Relational SQL Database like MySQL.

#### Pros:

-It is very easy to scale NoSQL.
-You can easily store very large amounts of data.
-It is much easier to both design, maintain, and repair a NoSQL database than is the case with a traditional SQL database.
-You can essentially extend NoSQL storage by simply "slapping on" extra storage.

#### Cons:

-NoSQL databases haven't been around here for so long. They might have some annoying bugs, poor documentation or unexpected behavior.
-You obviously don't have a universal language like SQL. So be prepared to change completely your app code base as you're moving towards another NoSQL solution.

#### NoSQL is still(in database terms) young, especially the newer models. This means that you have less established standards and risk an overall less stable database over time. One can compare it to different ways of constructing a house. The new way might be faster, but is it still not known if it is as stable long term as the old way.
Harder to extract data for analytics. The way many NoSQL databases, looking specifically at MongoDB here, are designed it is much harder to extract analytically relevant data such as "british male users age 20-29".
Explain reasons to add a layer like Mongoose, on top on of a schema-less database like MongoDB
Mongoose helps ensure the data added to MongoDB remains similar, eg. that there are no harmful differences between two "person" or two "house".

#### Explain the “6 Rules of Thumb: Your Guide Through the Rainbow” as to how and when you would use normalization vs. denormalization.
One: favor embedding unless there is a compelling reason not to
Two: needing to access an object on its own is a compelling reason not to embed it
Three: Arrays should not grow without bound. If there are more than a couple of hundred documents on the “many” side, don’t embed them; if there are more than a few thousand documents on the “many” side, don’t use an array of ObjectID references. High-cardinality arrays are a compelling reason not to embed.
Four: Don’t be afraid of application-level joins: if you index correctly and use the projection specifier (as shown in part 2) then application-level joins are barely more expensive than server-side joins in a relational database.
Five: Consider the write/read ratio when denormalizing. A field that will mostly be read and only seldom updated is a good candidate for denormalization: if you denormalize a field that is updated frequently then the extra work of finding and updating all the instances is likely to overwhelm the savings that you get from denormalizing.
Six: As always with MongoDB, how you model your data depends – entirely – on your particular application’s data access patterns. You want to structure your data to match the ways that your application queries and updates it.
#### Explain the difference between “Debug outputs” and application logging. What’s wrong with console.log(..) statements in our backend-code.
#### Demonstrate a system using application logging and “coloured” debug statements.
#### Explain, using relevant examples, concepts related to testing a REST-API using Node/JavaScript + relevant packages
#### Explain, using relevant examples, the Express concept; middleware.
#### Compare the express strategy toward (server side) templating with the one you used with Java on second semester.
#### Demonstrate a simple Server Side Rendering example using a technology of your own choice (pug, EJS, ..).
#### Explain, using relevant examples, your strategy for implementing a REST-API with Node/Express and show how you can "test" all the four CRUD operations programmatically using, for example, the Request package.
#### Explain, using relevant examples, about testing JavaScript code, relevant packages (Mocha etc.) and how to test asynchronous code.
#### Explain, preferably using an example, how you have deployed your node/Express applications, and which of the Express Production best practices you have followed.
