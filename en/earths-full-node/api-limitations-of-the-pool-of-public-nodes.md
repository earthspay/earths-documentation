# API limitations of the pool of public nodes

**Pool of public nodes **is a set of public nodes which provide data for our products \(Earths Wallet, DEX and others\) via REST API

[https://nodes.earths.ga](https://nodes.earths.ga/). You can use our public nodes to retreive the information from Earths' blockchain, but we recommend you to use your own nodes, because our pool has some limitations listed in the table below.

> [!NOTE]
> * There is a [Nginx-server](https://www.nginx.com) in front of each node in the pool, which limits the amount of connections and the number of requests per second a client is allowed to send to a node.
* In the table below regular expressions are used to express paths' names, such as, for example, ["\d+"](https://stackoverflow.com/questions/2841550/what-does-d-mean-in-regular-expression-terms). 
* The term burst below — is a Nginx's setting that defines the maximum size of the "splash" of the requests. If the amount of arriving requests per second exceeds the defined value, all the exceeding requests are put into a queue. The burst is the size of that queue. If the number of the exceeding requests begins to surpass the value of the burst, then new exceeding requests will not be put into the queue, and will be canceled with the error. Read more in [the documentation](http://nginx.org/en/docs/http/ngx_http_limit_req_module.html).

| Path | Maximum number of simultaneous connections to Nginx-server per IP-address (if limit will be exceeded, a client will get HTTP Status 503) | Maximum number of the requests to Nginx-server per IP-address |
| --- | :---: | :---: |
|  | 15 | 20 (burst 50) |
| /blocks/seq/\d+/\d+ | 1 | 1 |
| /blocks/at/.+ | 1 | 1 |
|/blocks/last<br/>/scorex/version<br/>/scorex/status<br/>/consensus/algo<br/>/consensus/basetarget<br/>/earths/address<br/>/transactions/address/.+/limit/.+<br/>/addresses/validate/.+<br/>/blocks/signature/.+<br/>/blocks/delay/.+/.+<br/>/consensus/generatingbalance/.+<br/>/earths/external-payment<br/>/peers/connected<br/>/peers/all<br/>/node/version<br/>/node/status<br/>/addresses/effectiveBalance/.+<br/>/assets/broadcast/issue<br/>/assets/broadcast/reissue<br/>/assets/broadcast/transfer<br/>/earths/broadcast-signed-payment.+<br/>/earths/external-payment<br/>/earths/broadcast-signed-payment<br/>/leasing/broadcast/lease<br/>/leasing/broadcast/cancel<br/>/alias/.+<br/>/assets/broadcast/burn |  100|  20 (burst 50)
| /transactions/info/.+ | 15 | 20 (burst 50) |
| ![](../_assets/3.png)| 15 | 20 (burst 50)
| ![](../_assets/4.png)| 15 | 20 (burst 50)
| /utils/script/decompile  | <span style="color:red">The path is temporarily unavailable</span>| <span style="color:red">The path is temporarily unavailable</span>|




