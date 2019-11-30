# google_aiy
Just a few notes on setting up the aiy voice kit on a pi-zero w.



1) Main Page [AIY Voice Kit](https://aiyprojects.withgoogle.com/voice/) and setup credentials.
2) Fix Pulse Audio
```
sudo sed -i -e "s/^load-module module-suspend-on-idle/#load-module module-suspend-on-idle/" /etc/pulse/default.pa
pulseaudio --kill
pulseaudio --start
```
3) Start google assistant 
```
cd /home/pi/AIY-voice-kit-python/src/examples/voice
./assistant_grpc_demo.py
```
4) Set it as a service on boot
```
# Install:
#    sudo ln -s `pwd`/assistant_grpc_demo.service /lib/systemd/system
#    sudo systemctl daemon-reload
#
# Start on each boot:
#    sudo systemctl enable assistant_grpc_demo.service
#
# Start right now:
#    sudo systemctl start assistant_grpc_demo.service
```
# References

* [AIY Voice Kit](https://aiyprojects.withgoogle.com/voice/) - Voice kit manual
* [aiyprojects-raspbian](https://github.com/google/aiyprojects-raspbian/releases) - Raspberry Pi Images
