Nginx
=====

Optimise for production
:::::::::::::::::::::::

Some tips.

* https://gist.github.com/denji/8359866

K8S ingresses based on nginx. Even out of K8S, the configuration templates can be used as a source of information.

* https://github.com/kubernetes/ingress-nginx
* https://github.com/nginxinc/kubernetes-ingress

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
