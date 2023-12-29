# codeigniter4-websocket

Corrigir erro de wss no nginx aapanel
criar um proxy reverso apontando para o http://localhost:8282
nas config do proxy colocar isto:

location ^~ /
{
    proxy_pass http://localhost:8282;
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection "upgrade";
    proxy_read_timeout 3600s;
}
