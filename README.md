password-privacy
================

Client-side hashing of passwords for enhanced password privacy.

Intent: use JavaScript to hash passwords in the browser so that they are never transmitted in plaintext form. That is, even snopping the network packets will not reveal the password as typed into the browser.

- By including username in the hash, the hash will be unique on this server, even if another user on the site has the same password.

- By including a site-specific salt in the hash, the hash will not be the same as the same username/password combination on another site, even if that site uses the same hashing scheme.

While this does not protect against replay attacks, let alone dictionary attacks or other guesses of typed passwords, (and thus doesn't necessarily make it harder to log in as this user on THIS site), it does keep the original typed password private.

That is, it ensures that intercepting the network packets for one user on one server will not enable logins for the same user on other servers.

This is especially beneficial if the site is not using https and/or the server does not already hash passwords server-side for storage (though any site with a user login should really be doing both).

I believe keeping passwords super-private is critical, because username (which is usually public or easily guessable) plus password generally gives full access to every bit of the user's information stored on a site, in addition to full control over it (ie, enabling deleting, changing, or addig to that information, changing password to lock the legitimate user out, etc.).

Furthermore, most people use the same username/password combination on more than one site. So a password discovered for one site can often give access to MANY sites.

In addition, many, many sites with logins do not use https and may not even hash the stored passwords on the server, making users' plaintext passwords readily accessible to many hackers.


