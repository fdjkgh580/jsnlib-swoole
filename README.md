# swoole
輔助 [Swoole](https://github.com/swoole/swoole-src) 的工具

## 用法
監聽 WebSocket 訊息事件

````php 
$ws = new swoole_websocket_server("0.0.0.0", 8080); 

$ws->on('message', function ($ws, $frame) {

 	\Jsnlib\Swoole::push_all([
		'ws'           => $ws,
		'self'         => $frame->fd,
		'is_send_self' => false,
		'data'         => $frame->data
 	]);

});
````
## 參數說明
- ws：Websocket 物件
- self: 當前連接的對象
- is_send_self: 是否要發送給自己？建議使用 false
- data: 發送的數據
