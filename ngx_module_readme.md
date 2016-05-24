ngx模块编写与使用：
1、将模块代码和config文件置于同一目录
例如：ngx_http_hello_module
2、config文件内容
ngx_addon_name=ngx_http_hello_module
HTTP_MODULES="$HTTP_MODULES ngx_http_hello_module"
NGX_ADDON_SRCS="$NGX_ADDON_SRCS $ngx_addon_dir/ngx_http_hello_module.c"
3、模块编译
./configure –prefix=[nginx source codes dir] –add-module=[module dir]
4、服务器配置文件
location /hello {
                hello_string yottapeng;
                hello_counter on;
}
