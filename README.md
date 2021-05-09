<h1 align='center'>How to create service in linux</h1>
<ol>
	<li>Go to '/lib/systemd/system/'</li>
	<ul><li><b><i>cd /lib/systemd/system/</b></i></li></ul>
	<li>And create file in this directory (*.service)</li>
	<ul><li><b><i>vim super_name.service</b></i></li></ul>
	<li>Write your service:</li>
	<p align='center' style='font-fize:24px;'>
		<pre>
		[Unit]
		Description=Start server for update all orders in DataBase
		After=mariadb.service
		[Service]
		Environment=PYTHONUNBUFFERED=true
		Type=notify
		#Type=idle
		#ExecStartPre=/root/server-idealist/bin/activate
		ExecStart=/root/server-idealist/bin/python /root/server-idealist/loop.py
		Restart=always
		WatchdogSec=15
		[Install]
		WantedBy=multi-user.target
		</pre>
	</p>
</ol>
