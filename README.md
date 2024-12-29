# Docker GNU Radio

Build :  
for v3.7 = sudo docker build -t ubuntu:gnuradio-v3.7 .  
for v3.8 = sudo docker build -t ubuntu:gnuradio-v3.8 .  
for v3.9 = sudo docker build -t ubuntu:gnuradio-v3.9 .  

for v3.7 Transmitter = sudo docker build -t ubuntu:gnuradio-v3.7-transmitter .  
for v3.7 Receiver = sudo docker build -t ubuntu:gnuradio-v3.7-receiver .  

Run :  
for v3.7 transmitter :  
sudo docker run \  
--net=host \  
--env="DISPLAY" \  
--volume="$HOME/.Xauthority:/root/.Xauthority:rw" \  
--privileged \  
--device=/dev/bus/usb:/dev/bus/usb \  
-v /dev/bus/usb:/dev/bus/usb \  
--device=/dev/snd \  
-v persistent-37-transmitter:/home/gnuradio/persistent \  
--group-add=audio \  
-it ubuntu:gnuradio-v3.7-transmitter bash  

for v3.7 receiver :  
sudo docker run \  
--net=host \  
--env="DISPLAY" \  
--volume="$HOME/.Xauthority:/root/.Xauthority:rw" \  
--privileged \  
--device=/dev/bus/usb:/dev/bus/usb \  
-v /dev/bus/usb:/dev/bus/usb \  
--device=/dev/snd \  
-v persistent-37-receiver:/home/gnuradio/persistent \  
--group-add=audio \  
-it ubuntu:gnuradio-v3.7-receiver bash  

 
