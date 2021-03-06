# go-sharp

The go-sharp(go-srs-http-advanced-reverse-proxy) is the proxy for SRS HTTP FLV.

## Usage

<strong>Step 1: Setup GO env.</strong>

About how to set $GOPATH, read [prepare go](http://blog.csdn.net/win_lin/article/details/40618671).

<strong>Step 2: Get go-sharp and build it.</strong>

To clone from github, build, install to $GOPATH and build go-sharp:

```
go get github.com/simple-rtmp-server/go-sharp
```

<strong>Step 3: Start go-sharp proxy.</strong>

For linux or unix:

```
$GOPATH/bin/go-sharp 8088 8 8080,8081,8082
```

Or, for windows:

```
%GOPATH%\bin\go-sharp.exe 8088 8 8080,8081,8082
```

<strong>Step 4: Start SRS HTTP FLV cluster.</strong>

About how to start HTTP FLV cluster of SRS, read wiki([CN][v2_CN_SampleHttpFlvCluster], [EN][v2_EN_SampleHttpFlvCluster])

<strong>Step 5: Play the proxy HTTP FLV stream.</strong>

The HTTP FLV streams:

```
SRS Origin: http://127.0.0.1:8080/live/livestream.flv
SRS Edge1: http://127.0.0.1:8081/live/livestream.flv
SRS Edge2: http://127.0.0.1:8082/live/livestream.flv
go-sharp proxy: http://127.0.0.1:8088/live/livestream.flv
```

You can use [vlc][vlc] or online jwplayer players to play [SRS Origin][jwplayer-flv],
[SRS Edge1][jwplayer-flv-8081], [SRS Edge2][jwplayer-flv-8082] and [go-sharp proxy][jwplayer-flv-8088].

Remark: Please replace the server ip by yours.

## Features

* Reverse HTTP proxy for SRS HTTP FLV cluster.
* Load balance for these proxe SRS server.
* Auto detect the alive of proxy SRS server.
* [plan] Auto detect the load of proxy SRS server.
* [plan] HLS DRM token, generate and verify the token in ts url.

## Performance

Comming soon ...

## IDE

Go: http://www.golangtc.com/download

JetBrains IntelliJ IDEA: http://www.jetbrains.com/idea/download

Idea Plugin: https://github.com/go-lang-plugin-org/go-lang-idea-plugin

Winlin 2015.5


[v2_CN_SampleHttpFlvCluster]: https://github.com/simple-rtmp-server/srs/wiki/v2_CN_SampleHttpFlvCluster
[v2_EN_SampleHttpFlvCluster]: https://github.com/simple-rtmp-server/srs/wiki/v2_EN_SampleHttpFlvCluster
[vlc]: http://www.videolan.org/
[jwplayer-flv]: http://www.ossrs.net/players/jwplayer6.html?stream=livestream.flv&server=127.0.0.1&hls_port=8080&hls_autostart=true
[jwplayer-flv-8081]: http://www.ossrs.net/players/jwplayer6.html?stream=livestream.flv&server=127.0.0.1&hls_port=8081&hls_autostart=true
[jwplayer-flv-8082]: http://www.ossrs.net/players/jwplayer6.html?stream=livestream.flv&server=127.0.0.1&hls_port=8082&hls_autostart=true
[jwplayer-flv-8088]: http://www.ossrs.net/players/jwplayer6.html?stream=livestream.flv&server=127.0.0.1&hls_port=8088&hls_autostart=true
