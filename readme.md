# Hashget

Retrieve all the tweets from Twitter based on keyword

### Installation

Hashget requires [PHP](http://www.php.net/) >= 5.6.4 and Redis Server to run.

Download and extract the [latest pre-built release](https://github.com/kavanpancholi/hashget).

Install the dependencies and devDependencies and start the server.

```sh
$ composer update
$ cp .env-example .env
$ php artisan key:generate
```
Create database named hashget and update the database connectivity in .env file

[Create Twitter App](https://apps.twitter.com/app/new) and grab the keys and access tokens. Add them to .env file

### Make it work
Start Redis server using this command
```
$ redis-server
```

To create database tables (Migrate Database)
```
$ php artisan migrate
```
To stream tweets in queue (Note: It will not retrieve the tweets yet)
```
$ php artisan stream {keyword}
```
e.g. php artisan stream India

Note: For the hash keyword or multiple words use quotes
e.g. php artisan stream "India" or php artisan stream "Cricket 2016"

To add queue (and add stream data into database)
```
$ php artisan queue:listen
```

### Todos
 - Create Scrolling tweets in homepage with scroll pagination
 - Autoscroll to from first tweets when pagination ends

License
----

MIT

**Free Software, Hell Yeah!**