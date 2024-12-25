# Docker GNU Radio

Build :  
docker build -t ubuntu:gnuradio-v3.7 .

Run :  
docker run --net=host --env="DISPLAY" --volume="$HOME/.Xauthority:/root/.Xauthority:rw" --privileged -v /dev/bus/usb/:/dev/bus/usb/ --device /dev/snd -v persistent-37:/home/gnuradio/persistent --group-add=audio -it ubuntu:gnuradio-v3.7 bash
