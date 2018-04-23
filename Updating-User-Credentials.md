We can simply update a user credentials using a POST request via Postman.

**Steps:**

1.	Boot up the back-end server.
2.	Open Postman or any other API Environment software of your choice.
3.	Run a GET request on http://dev.recruit.com:8030/crypt/pass
4.	Replace `pass` in the URL above with a password of your choice.
5.	Hit Send.
6.	The server will return you an encrypted alpha-numeric password that you can now use to update it on your Database, example shown below:

![Sample](https://i.imgur.com/cArmf9R.png)


## Advanced

If you'd like to update your username and other particulars, you can do so by updating it directly from the Database.
