Nginx
=====

Access-Control-Allow-Origin
:::::::::::::::::::::::::::

Ignored if out of the if block, don't know why (probably because if is evil).

.. code-block:: nginx

    location @backend {
      internal;
  
      if ($request_filename ~* \.(jpg|jpeg|gif|png|bmp|ico|pdf|flv|swf|txt|css|js|otf|eot|svg|ttf|woff|woff2|map)$) {
        expires 7d;
        add_header "Cache-control" "public";
        add_header "Access-Control-Allow-Origin" "*";
        access_log off;
      }
  
      include rdbp/proxy.conf;
  
      proxy_pass http://ngxps-backend:3080;
      proxy_pass_header Cache-Control;
    }
