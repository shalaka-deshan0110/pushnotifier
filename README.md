Laravel Push Notification Sample Application
=========

Using laravel Websockets to send push notifications to devices

Installation
----

#####Installation of laravel websockets.
beyondcode/laravel-websockets is a powerful Laravel package that empowers your application with WebSocket capabilities. It offers seamless integration for real-time communication, SSL support, Laravel Echo compatibility, and a debugging dashboard, making it an essential tool for building interactive and dynamic web applications. It works as a replacement for paid and subscription services like Pushe.r

```json
composer require beyondcode/laravel-websockets
```

 pusher/pusher-php-server, a PHP library that facilitates seamless communication with the Pusher Channels HTTP API, enabling real-time features in your applications without the need for the Pusher server infrastructure. Unlock the power of real-time updates with this standalone package.
```json∏
composer require pusher/pusher-php-server
```

Need to update .env with below sections. Laravel Websockets uses same names here as in Pusher package,so allowing transition from Websockets service to pusher without much hassle.
```json
BROADCAST_DRIVER=pusher
```

```json
PUSHER_APP_ID=12345
PUSHER_APP_KEY=12345
PUSHER_APP_SECRET=12345
PUSHER_APP_CLUSTER=mt1
```

Laravel WebSockets package comes with migrations file and a config file. Below commands will publish the websockets provider and complete migrations.
```json
php artisan vendor:publish --provider="BeyondCode\LaravelWebSockets\WebSocketsServiceProvider" --tag="migrations"
```

```json
php artisan migrate
```

```json
php artisan vendor:publish --provider="BeyondCode\LaravelWebSockets\WebSocketsServiceProvider" --tag="config"
```

Finally we can use websockets by running below command.
```json
php artisan websockets:serve
```
![Alt text](<Screenshot 2023-10-10 at 01.04.54.png>)
