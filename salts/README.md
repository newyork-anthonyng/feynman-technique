# Password Salts

We should not store passwords in plaintext in our database. If a hacker got access to our database, they would know our user's passwords.

> anthony@example.com, password123


Instead, we should store hashed passwords in our database.

> https://codesandbox.io/s/fervent-gauss-lzfj1?file=/src/App.js
> https://lzfj1.csb.app/

A hashing function is a one-way function. It means that it's very quick to hash an input, but it's very slow to get the original input from a hash.

This is awesome. If our database gets leaked, the hackers can't easily get the user's original passwords. That's perfect!

Except for rainbow tables.

Rainbow tables are hashes of popular or leaked passwords. If our user's passwords are in the rainbow table, their hashes will match the rainbow table.

> https://codesandbox.io/s/dazzling-night-leuds?file=/src/App.js
> https://leuds.csb.app/

Another issue is we can tell when different users have the same password. Their hashed password will be the same.

This is where password salts can help. Password salts are randomly generated strings. Each users has their own unique password salt. We "sprinkle" the salt (like the condiment salt) to the end of their password.

We hash the password and salt together, and store it in the database.

> https://codesandbox.io/s/pensive-tree-de7sk?file=/src/App.js
> https://de7sk.csb.app/

This is perfect. Rainbow tables are no longer effective. The hacker will have to brute force all passwords. 

Also, users can use the same password as each other. But the password salt makes their password hashes unique.
