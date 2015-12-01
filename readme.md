## scaling with haproxy and consul ##

goal is to scale with docker with an infinite amount of webservers

to start:
docker-machine ip dockervmname

docker-compose build
docker-compose up

consul ui: http://dockervmip:8500
haproxy stats: http://dockervmip:9000/haproxy_stats
website (just php posting hostname) http://dockervmip 