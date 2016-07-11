# Usage

## For Linux
```sh
# Docker
$ docker run -d --name tensorflow -p 8888:8888 -p 6006:6006 DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix hytssk/tensorflow
```

```sh
# NVIDIA Docker
$ nvidia-docker run -d --name tensorflow -p 8888:8888 -p 6006:6006 DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix hytssk/tensorflow:gpu
```

## For Windows(utilize [MobaXTerm](http://mobaxterm.mobatek.net/))
In boot2docker, 
```sh
# Docker
$ docker run -d --name tensorflow -p 8888:8888 -p 6006:6006 -p 10022:22 hytssk/tensorflow
```
```sh
# NVIDIA-Docker
$ nvidia-docker run -d --name tensorflow -p 8888:8888 -p 6006:6006 -p 10022:22 hytssk/tensorflow:gpu
```

After running container, 

+ Enter *Session Setting* of MobaXTerm
+ Edit three items
	+ Remote host: 192.168.99.100 
	+ specify username(check): developer
	+ port: 10022
+ Enter Password: developer
+ Edit *Excute Command*
	+ export DISPLAY=\`echo $SSH_CLIENT | cut -d' ' -f1\`:0.0
+ Check *Do not exit after commands ends*
+ Enter *OK*
