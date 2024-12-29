# Docker GNU Radio

Build :  
for v3.7 = docker build -t ubuntu:gnuradio-v3.7 .  
for v3.8 = docker build -t ubuntu:gnuradio-v3.8 .  
for v3.9 = docker build -t ubuntu:gnuradio-v3.9 .  

for v3.7 Transmitter = docker build -t ubuntu:gnuradio-v3.7-transmitter .  
for v3.7 Receiver = docker build -t ubuntu:gnuradio-v3.7-receiver .  

Run :  
docker run --net=host --env="DISPLAY" --volume="$HOME/.Xauthority:/root/.Xauthority:rw" --privileged -v /dev/bus/usb/:/dev/bus/usb/ --device /dev/snd -v persistent-37:/home/gnuradio/persistent --group-add=audio -it ubuntu:gnuradio-v3.7 bash
atau  
sudo docker run \
  --net=host \
  --env="DISPLAY" \
  --volume="$HOME/.Xauthority:/root/.Xauthority:rw" \
  --privileged \
  --device=/dev/bus/usb:/dev/bus/usb \
  -v /dev/bus/usb:/dev/bus/usb \
  --device=/dev/snd \
  -v persistent-37:/home/gnuradio/persistent \
  --group-add=audio \
  -it ubuntu:gnuradio-v3.7 bash
