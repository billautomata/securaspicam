# securaspicam
ssh tunneled ip camera solution based on raspberry pi

### hardware description
* [ ip camera ] 
* [ ethernet ] 
* [ raspi ]
* [ wifi ]
* [ client router ]
* [ internet ]
* [ office router ]
* [ wifi / ethernet ]
* [ server ]

### software description
* `raspi` acts as a reverse proxy for the `ip camera` on protected wired network connection `ethernet`
* `raspi` exposes the ip camera stream only to connections on the localhost, shielding the `ip camera` from the wider network
* `server` creates an ssh connection to `raspi` 
  * the ssh connection opens a tunnel from a local port on the server to a remote port on the `raspi`
  * it is the same port the `raspi` is reverse proxying the `ip camera` streams
* `server` connects to the tunnel on the local port an connects to the `ip camera` ( http://localhost:9000/video.cgi )
