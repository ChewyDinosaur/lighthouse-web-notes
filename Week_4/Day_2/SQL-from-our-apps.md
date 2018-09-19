# SQL from our Apps

The theme of today was based on [this video](https://www.youtube.com/watch?v=O7oD_oX-Gio) which represents how we are combining PostgreSQL and JavaScript.

We started off by learning about parameterized queries using the following code:
```
const { Client } = require('pg');
const client = new Client({database: 'my_app'});

client.connect();

client.query('SELECT * FROM users WHERE username=$1', ['don'], (err, res) => {
  console.log(err ? err.stack : res.rows[0].username); // don
  client.end();
});
```
Then we progressed on to building a basic hockey db query tool. We went from there to building a CLI tool to search the db for a particular player.

Here is the [documentation](https://node-postgres.com/) for the pg npm module.

And of course: [Little Bobby Tables](https://xkcd.com/327/)

Code from today's lecture: https://gist.github.com/34174643736d3a5a2b034a582abaa26a