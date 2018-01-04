# nginx-hls

###### Install Homebrew

`ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

brew cleanup

brew doctor

brew tap homebrew/nginx

###### intstall nginx

`brew install nginx-full --with-rtmp-module`

brew info nginx-full

cd /usr/local/etc/nginx

modify nginx config

`sudo nginx -s reload`

sudo nginx -s stop

sudo php-fpm


###### install ffmpeg

`brew install ffmpeg`

ffmpeg -re -i /Users/liuhong/Movies/Demo.mov -vcodec copy -f flv rtmp://localhost:1935/rtmplive/home

`ffmpeg -re -i /Users/herry/Desktop/14564977406580.mp4 -vcodec libx264 -acodec aac -f flv rtmp://localhost:1935/hls/home`

###### examine in nginx server
cd home

mkdir rtmp

mkdir hls


###### examine in browser
http://127.0.0.1:8081/stat 

###### examine in IOS
http://localhost:8081/rtmp/home.m3u8

    import AVFoundation
    
    let container = UIView(frame: CGRect(x: 5, y: 80, width: 300, height: 200))
    container.backgroundColor = UIColor.cyan
    view.addSubview(container)
        
    let url = URL(string: "http://localhost:8081/rtmp/home.m3u8")
    let player = AVPlayer(url: url!)
        
    let layer = AVPlayerLayer(player: player)
    layer.frame = container.bounds
    container.layer.addSublayer(layer)
        
    player.play()


###### examine in VLC software
rtmp://127.0.0.1:1935/hls/home






