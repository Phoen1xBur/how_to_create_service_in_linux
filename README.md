<h1 align='center'>How to create service in linux</h1>
<ol>
	<li>Go to '/lib/systemd/system/'</li>
	<ul><li><b><i>cd /lib/systemd/system/</b></i></li></ul>
	<li>And create file in this directory (*.service)</li>
	<ul><li><b><i>vim super_name.service</b></i></li></ul>
	<li>Write your service:</li>
	<p>
		<pre>
[Unit]
Description=Super puper description your service
After=mariadb.service  # if your service need work on DB
[Service]
Environment=PYTHONUNBUFFERED=true  # If u need to python print info in status service
Type=notify
#ExecStartPre=/root/server-idealist/bin/activate  # If need pre start programm
# Path to python and path to python script need to start
ExecStart=/root/server-idealist/bin/python /root/server-idealist/loop.py  # Your programm(python script)
Restart=always
#WatchdogSec=15  # For check die programm or no
[Install]
WantedBy=multi-user.target
		</pre>
	</p>
	<li>Restart daemon</li>
	<ul><li><b><i>daemon-reload</b></i></li></ul>
	<li>Start programm</li>
	<ul><li><b><i>systemctl enable super_name.service</b></i></li></ul>
</ol>
