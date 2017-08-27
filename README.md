## Chatdemo
Chatdemo is a simple chatting example was developed in Laravel Framework 5.4 by using Pusher API and Laravel-Echo Broadcasting service. 
## Installation
**Open Terminal and run following command:**
``` markdown
$ composer install
```
**Rename `.env.example` file to `.env` and  create `homestead` database grant all privileges to `homestead` user identified by password `secret`**
``` markdown
DB_DATABASE=homestead
DB_USERNAME=homestead
DB_PASSWORD=secret
```
**Run following command to create unique `APP_KEY`**
```
$ pa key:generate
```
**Set Broadcast driver as pusher and Add following `PUSHER_APP` info by creating new account in Pusher site (https://pusher.com/)**
```markdown
BROADCAST_DRIVER=pusher
PUSHER_APP_ID=xxxxxx
PUSHER_APP_KEY=xxxxxxxxxxxxxxxxxxxx
PUSHER_APP_SECRET=xxxxxxxxxxxxxxxxxxxx
```
**Update pusher key, cluster and encrypted in `bootstrap.js` file as given below:**
```
window.Echo = new Echo({
    broadcaster: 'pusher',
    key: 'xxxxxxxxxxxxxxxxxxxx',
    cluster: 'xxx', //check on your pusher account-> 'your app' -> 'App Keys'
    encrypted: xxxxx, //If you are using 'http:' or  'https:'
});
```
**Update cluster and encrypted value same as above in `broadcasting.php`:**
 ```
pusher' => [
    	   'driver' => 'pusher',
    	   'key' => env('PUSHER_APP_KEY'),
    	   'secret' => env('PUSHER_APP_SECRET'),
    	   'app_id' => env('PUSHER_APP_ID'),
    	   'options' => [
    			'cluster' => 'xxx',
    			'encrypted' => xxx,
    	   	],
   	]
 ```
**Run Following Command to download and build the required scripts dependencies** 
```
$ npm install 
$ npm run dev
```
**Run server and Enjoy Chatting**   :smiley:
```
$ pa serve
```
