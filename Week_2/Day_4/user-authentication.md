# User Authentication

Credential - gives credibility and identity

Public credential - username, email address, something that theoretically anyone could know, without compromising your account. This is what identifies the account to the system.

Private credential - Password (999/1000). This is what "secures" your account from other people.

POST - So that the info submitted is hidden from the client's display

## Authentication workflow

* Use the public credential to look up the account
* Verify the private credential
* If successful a. Redirect to whatever the root page (index) is.
* If not successful a. Redirect back to login page b. Show an error (Invalid credentials, never bad password)
Here is the documentation for [cookie-session.](https://www.npmjs.com/package/cookie-session)

Here is the documentation for [bcrypt.](https://www.npmjs.com/package/bcrypt)

Here is the repo with the app we built today: https://github.com/donburks/aug272018_w2d4

