
default:	build

clean:
	rm -rf Makefile objs

.PHONY:	default clean

build:
	$(MAKE) -f objs/Makefile

install:
	$(MAKE) -f objs/Makefile install

modules:
	$(MAKE) -f objs/Makefile modules

upgrade:
	../../nginx_server/sbin/nginx -t

	kill -USR2 `cat ../../nginx_server/logs/nginx.pid`
	sleep 1
	test -f ../../nginx_server/logs/nginx.pid.oldbin

	kill -QUIT `cat ../../nginx_server/logs/nginx.pid.oldbin`

.PHONY:	build install modules upgrade
