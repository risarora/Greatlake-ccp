```
[15/Nov/2020 07:56:51] "GET /manager/html HTTP/1.1" 404 1984
*********************** Incoming request *****************************   Req meta item: wsgi.version (1, 0)
  Req meta item: RUN_MAIN true
  Req meta item: SERVER_PROTOCOL HTTP/1.1
  Req meta item: SERVER_SOFTWARE WSGIServer/0.1 Python/2.7.17
  Req meta item: LC_CTYPE C.UTF-8
  Req meta item: SCRIPT_NAME 
  Req meta item: LESSOPEN | /usr/bin/lesspipe %s
  Req meta item: SSH_CLIENT 122.182.216.105 51785 22
  Req meta item: REQUEST_METHOD POST
  Req meta item: LOGNAME ubuntu
  Req meta item: USER ubuntu
  Req meta item: HOME /home/ubuntu
  Req meta item: QUERY_STRING 
  Req meta item: PATH /home/ubuntu/.virtualenvs/djangodev/bin:/home/ubuntu/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
  Req meta item: PS1 (djangodev) \[\e]0;\u@\h: \w\a\]${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ 
  Req meta item: wsgi.errors <open file '<stderr>', mode 'w' at 0x7f808ebf5270>
  Req meta item: LANG C.UTF-8
  Req meta item: TERM xterm-256color
  Req meta item: SHELL /bin/bash
  Req meta item: TZ UTC
  Req meta item: SERVER_NAME ip-172-31-50-17.ec2.internal
  Req meta item: REMOTE_ADDR 72.21.217.96
  Req meta item: XDG_DATA_DIRS /usr/local/share:/usr/share:/var/lib/snapd/desktop
  Req meta item: wsgi.url_scheme http
  Req meta item: SERVER_PORT 8080
  Req meta item: CONTENT_LENGTH 1192
  Req meta item: XDG_RUNTIME_DIR /run/user/1000
  Req meta item: wsgi.file_wrapper wsgiref.util.FileWrapper
  Req meta item: VIRTUAL_ENV /home/ubuntu/.virtualenvs/djangodev
  Req meta item: wsgi.input <socket._fileobject object at 0x7f80886709d0>
  Req meta item: wsgi.multithread True
  Req meta item: XDG_SESSION_ID 31
  Req meta item: _ /home/ubuntu/.virtualenvs/djangodev/bin/python
  Req meta item: SSH_CONNECTION 122.182.216.105 51785 172.31.50.17 22
  Req meta item: LESSCLOSE /usr/bin/lesspipe %s %s
  Req meta item: GATEWAY_INTERFACE CGI/1.1
  Req meta item: wsgi.run_once False
  Req meta item: SSH_TTY /dev/pts/0
  Req meta item: OLDPWD /home/ubuntu
  Req meta item: wsgi.multiprocess False
  Req meta item: SHLVL 1
  Req meta item: PWD /opt/docproc-new
  Req meta item: DJANGO_SETTINGS_MODULE docproc.settings
  Req meta item: CONTENT_TYPE text/plain; charset=UTF-8
  Req meta item: MAIL /var/mail/ubuntu
  Req meta item: LS_COLORS rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=30;41:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.Z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:
  Req meta item: REMOTE_HOST 
  Req meta item: PATH_INFO /sns
POST HTTP/1.1
Content-Length: 1192
Content-Type: text/plain; charset=UTF-8
Headers: X-Amz-Sns-Topic-Arn: arn:aws:sns:us-east-1:916317828206:S3toEC2Topic
X-Amz-Sns-Message-Type: Notification
X-Amz-Sns-Subscription-Arn: arn:aws:sns:us-east-1:916317828206:S3toEC2Topic:30e9ea54-8ee4-4d3a-afc9-2afd26a9f1fe
X-Amz-Sns-Message-Id: 35e278f1-88fe-588f-8305-20db6bfd46d3
User-Agent: Amazon Simple Notification Service Agent
Host: 54.146.93.185:8080
Connection: Keep-Alive
Accept-Encoding: gzip,deflate

Body: {
  "Type" : "Notification",
  "MessageId" : "35e278f1-88fe-588f-8305-20db6bfd46d3",
  "TopicArn" : "arn:aws:sns:us-east-1:916317828206:S3toEC2Topic",
  "Subject" : "Amazon S3 Notification",
  "Message" : "{\"Service\":\"Amazon S3\",\"Event\":\"s3:TestEvent\",\"Time\":\"2020-11-15T08:03:15.970Z\",\"Bucket\":\"glsource\",\"RequestId\":\"E0EFE566FF3898A8\",\"HostId\":\"1EOA2REy/4+fkzq30H9GBVNFQM1Yzy7WDlx6Lpl0skUOUoVyGaFss4VLgY/FghQuaae3coez0dE=\"}",
  "Timestamp" : "2020-11-15T08:03:15.993Z",
  "SignatureVersion" : "1",
  "Signature" : "Ih+owWDYMxpIH6TNOphuPuOJgm0wath8U76G4I8l6Zbhq/NGNFd4GDZy687NAqikCS9x0szcAGheeNSPkVkPG5jw1VM9z67nzY4vCzJKRO3t2U4Oz6q0bL7ULTy5swNHdhKaXu3DXCcuxzBMkbezsiGy39PMlQ8LcXm5/RErF43IsE7RrIKfhaBGQ1x05744NoMVbkAdH0vllV2k9gJb+E485XDOWALnhyI9JnRdB5a3clUvnO1aXe5UFxqQCqJpOf4cg7sleHoYFTl56v+2LPEq9KEjbeWj0rFv7OSaoavS2ICLPFsu+IT0CYpm2NA+hVXGHVpTDS3puaIh3hUgGQ==",
  "SigningCertURL" : "https://sns.us-east-1.amazonaws.com/SimpleNotificationService-a86cb10b4e1f29c941702d737128f7b6.pem",
  "UnsubscribeURL" : "https://sns.us-east-1.amazonaws.com/?Action=Unsubscribe&SubscriptionArn=arn:aws:sns:us-east-1:916317828206:S3toEC2Topic:30e9ea54-8ee4-4d3a-afc9-2afd26a9f1fe"
}
Request method = POST
The S3 JSON is  {
  "Type" : "Notification",
  "MessageId" : "35e278f1-88fe-588f-8305-20db6bfd46d3",
  "TopicArn" : "arn:aws:sns:us-east-1:916317828206:S3toEC2Topic",
  "Subject" : "Amazon S3 Notification",
  "Message" : "{\"Service\":\"Amazon S3\",\"Event\":\"s3:TestEvent\",\"Time\":\"2020-11-15T08:03:15.970Z\",\"Bucket\":\"glsource\",\"RequestId\":\"E0EFE566FF3898A8\",\"HostId\":\"1EOA2REy/4+fkzq30H9GBVNFQM1Yzy7WDlx6Lpl0skUOUoVyGaFss4VLgY/FghQuaae3coez0dE=\"}",
  "Timestamp" : "2020-11-15T08:03:15.993Z",
  "SignatureVersion" : "1",
  "Signature" : "Ih+owWDYMxpIH6TNOphuPuOJgm0wath8U76G4I8l6Zbhq/NGNFd4GDZy687NAqikCS9x0szcAGheeNSPkVkPG5jw1VM9z67nzY4vCzJKRO3t2U4Oz6q0bL7ULTy5swNHdhKaXu3DXCcuxzBMkbezsiGy39PMlQ8LcXm5/RErF43IsE7RrIKfhaBGQ1x05744NoMVbkAdH0vllV2k9gJb+E485XDOWALnhyI9JnRdB5a3clUvnO1aXe5UFxqQCqJpOf4cg7sleHoYFTl56v+2LPEq9KEjbeWj0rFv7OSaoavS2ICLPFsu+IT0CYpm2NA+hVXGHVpTDS3puaIh3hUgGQ==",
  "SigningCertURL" : "https://sns.us-east-1.amazonaws.com/SimpleNotificationService-a86cb10b4e1f29c941702d737128f7b6.pem",
  "UnsubscribeURL" : "https://sns.us-east-1.amazonaws.com/?Action=Unsubscribe&SubscriptionArn=arn:aws:sns:us-east-1:916317828206:S3toEC2Topic:30e9ea54-8ee4-4d3a-afc9-2afd26a9f1fe"
}
Exiting by Rishi
[15/Nov/2020 08:03:16] "POST /sns HTTP/1.1" 200 43
*********************** Incoming request *****************************   Req meta item: wsgi.version (1, 0)
  Req meta item: RUN_MAIN true
  Req meta item: SERVER_PROTOCOL HTTP/1.1
  Req meta item: SERVER_SOFTWARE WSGIServer/0.1 Python/2.7.17
  Req meta item: LC_CTYPE C.UTF-8
  Req meta item: SCRIPT_NAME 
  Req meta item: LESSOPEN | /usr/bin/lesspipe %s
  Req meta item: SSH_CLIENT 122.182.216.105 51785 22
  Req meta item: REQUEST_METHOD POST
  Req meta item: LOGNAME ubuntu
  Req meta item: USER ubuntu
  Req meta item: HOME /home/ubuntu
  Req meta item: QUERY_STRING 
  Req meta item: PATH /home/ubuntu/.virtualenvs/djangodev/bin:/home/ubuntu/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
  Req meta item: PS1 (djangodev) \[\e]0;\u@\h: \w\a\]${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ 
  Req meta item: wsgi.errors <open file '<stderr>', mode 'w' at 0x7f808ebf5270>
  Req meta item: LANG C.UTF-8
  Req meta item: TERM xterm-256color
  Req meta item: SHELL /bin/bash
  Req meta item: TZ UTC
  Req meta item: SERVER_NAME ip-172-31-50-17.ec2.internal
  Req meta item: REMOTE_ADDR 72.21.217.109
  Req meta item: XDG_DATA_DIRS /usr/local/share:/usr/share:/var/lib/snapd/desktop
  Req meta item: wsgi.url_scheme http
  Req meta item: SERVER_PORT 8080
  Req meta item: CONTENT_LENGTH 1803
  Req meta item: XDG_RUNTIME_DIR /run/user/1000
  Req meta item: wsgi.file_wrapper wsgiref.util.FileWrapper
  Req meta item: VIRTUAL_ENV /home/ubuntu/.virtualenvs/djangodev
  Req meta item: wsgi.input <socket._fileobject object at 0x7f8088670f50>
  Req meta item: wsgi.multithread True
  Req meta item: XDG_SESSION_ID 31
  Req meta item: _ /home/ubuntu/.virtualenvs/djangodev/bin/python
  Req meta item: SSH_CONNECTION 122.182.216.105 51785 172.31.50.17 22
  Req meta item: LESSCLOSE /usr/bin/lesspipe %s %s
  Req meta item: GATEWAY_INTERFACE CGI/1.1
  Req meta item: wsgi.run_once False
  Req meta item: SSH_TTY /dev/pts/0
  Req meta item: OLDPWD /home/ubuntu
  Req meta item: wsgi.multiprocess False
  Req meta item: SHLVL 1
  Req meta item: PWD /opt/docproc-new
  Req meta item: DJANGO_SETTINGS_MODULE docproc.settings
  Req meta item: CONTENT_TYPE text/plain; charset=UTF-8
  Req meta item: MAIL /var/mail/ubuntu
  Req meta item: LS_COLORS rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=30;41:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.Z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:
  Req meta item: REMOTE_HOST 
  Req meta item: PATH_INFO /sns
POST HTTP/1.1
Content-Length: 1803
Content-Type: text/plain; charset=UTF-8
Headers: X-Amz-Sns-Topic-Arn: arn:aws:sns:us-east-1:916317828206:S3toEC2Topic
X-Amz-Sns-Message-Type: Notification
X-Amz-Sns-Subscription-Arn: arn:aws:sns:us-east-1:916317828206:S3toEC2Topic:30e9ea54-8ee4-4d3a-afc9-2afd26a9f1fe
X-Amz-Sns-Message-Id: ff21171f-dcef-518f-8f2b-4f3539b8af1a
User-Agent: Amazon Simple Notification Service Agent
Host: 54.146.93.185:8080
Connection: Keep-Alive
Accept-Encoding: gzip,deflate

Body: {
  "Type" : "Notification",
  "MessageId" : "ff21171f-dcef-518f-8f2b-4f3539b8af1a",
  "TopicArn" : "arn:aws:sns:us-east-1:916317828206:S3toEC2Topic",
  "Subject" : "Amazon S3 Notification",
  "Message" : "{\"Records\":[{\"eventVersion\":\"2.1\",\"eventSource\":\"aws:s3\",\"awsRegion\":\"us-east-1\",\"eventTime\":\"2020-11-15T08:13:04.536Z\",\"eventName\":\"ObjectCreated:Put\",\"userIdentity\":{\"principalId\":\"AWS:AROA5KWGMORXG74KLG3YG:user1025256=risarora@gmail.com\"},\"requestParameters\":{\"sourceIPAddress\":\"122.182.216.105\"},\"responseElements\":{\"x-amz-request-id\":\"0D215F68CE59BF27\",\"x-amz-id-2\":\"QRKM2JiHPtMPkRtlmn7rYxRN2dMVm4WSrun8MXw6dfT/L0arRp2pEoGhwLNTQw9NUSub+mGAKj6d7KMeffajLNMQbWf3DqHU\"},\"s3\":{\"s3SchemaVersion\":\"1.0\",\"configurationId\":\"S3PutEvent\",\"bucket\":{\"name\":\"glsource\",\"ownerIdentity\":{\"principalId\":\"A1ZZHHRVDSWEJQ\"},\"arn\":\"arn:aws:s3:::glsource\"},\"object\":{\"key\":\"docproc-invoice.txt\",\"size\":572,\"eTag\":\"2fafdc4705f330664733b544dbcabc43\",\"sequencer\":\"005FB0E315901245E5\"}}}]}",
  "Timestamp" : "2020-11-15T08:13:11.219Z",
  "SignatureVersion" : "1",
  "Signature" : "S22JEOC68BWbTDPVc8+80VIkmvraOAnPu86e8Vdshq6O3VNL8cagO5EiT+AeG1XF9eJI/HRVn3OCf2HkI8WtQPy0xs4yNNNExsXOdZYUxAXwmRUo4PrsDYc0qCjsTJFWCyrWlBBJSJMuIgz4MHPK9zQ5eawywmqHHvVt8k9rEEBYkL41O+LM/hj9oq3P8gLYwkn1GnxTU7H/ptgmrVZBVbua0ylQXxSFRudF7hbJwZgYKM7UoISiIx9E6WgXo2K7po57xAQbXz8wMssHh74i/Ey29NChJefVKtNzqlkM2h1bWjCruWXG15c1vY99OdDHQRdRj2+ohLPxdqFb0HP8xw==",
  "SigningCertURL" : "https://sns.us-east-1.amazonaws.com/SimpleNotificationService-a86cb10b4e1f29c941702d737128f7b6.pem",
  "UnsubscribeURL" : "https://sns.us-east-1.amazonaws.com/?Action=Unsubscribe&SubscriptionArn=arn:aws:sns:us-east-1:916317828206:S3toEC2Topic:30e9ea54-8ee4-4d3a-afc9-2afd26a9f1fe"
}
Request method = POST
The S3 JSON is  {
  "Type" : "Notification",
  "MessageId" : "ff21171f-dcef-518f-8f2b-4f3539b8af1a",
  "TopicArn" : "arn:aws:sns:us-east-1:916317828206:S3toEC2Topic",
  "Subject" : "Amazon S3 Notification",
  "Message" : "{\"Records\":[{\"eventVersion\":\"2.1\",\"eventSource\":\"aws:s3\",\"awsRegion\":\"us-east-1\",\"eventTime\":\"2020-11-15T08:13:04.536Z\",\"eventName\":\"ObjectCreated:Put\",\"userIdentity\":{\"principalId\":\"AWS:AROA5KWGMORXG74KLG3YG:user1025256=risarora@gmail.com\"},\"requestParameters\":{\"sourceIPAddress\":\"122.182.216.105\"},\"responseElements\":{\"x-amz-request-id\":\"0D215F68CE59BF27\",\"x-amz-id-2\":\"QRKM2JiHPtMPkRtlmn7rYxRN2dMVm4WSrun8MXw6dfT/L0arRp2pEoGhwLNTQw9NUSub+mGAKj6d7KMeffajLNMQbWf3DqHU\"},\"s3\":{\"s3SchemaVersion\":\"1.0\",\"configurationId\":\"S3PutEvent\",\"bucket\":{\"name\":\"glsource\",\"ownerIdentity\":{\"principalId\":\"A1ZZHHRVDSWEJQ\"},\"arn\":\"arn:aws:s3:::glsource\"},\"object\":{\"key\":\"docproc-invoice.txt\",\"size\":572,\"eTag\":\"2fafdc4705f330664733b544dbcabc43\",\"sequencer\":\"005FB0E315901245E5\"}}}]}",
  "Timestamp" : "2020-11-15T08:13:11.219Z",
  "SignatureVersion" : "1",
  "Signature" : "S22JEOC68BWbTDPVc8+80VIkmvraOAnPu86e8Vdshq6O3VNL8cagO5EiT+AeG1XF9eJI/HRVn3OCf2HkI8WtQPy0xs4yNNNExsXOdZYUxAXwmRUo4PrsDYc0qCjsTJFWCyrWlBBJSJMuIgz4MHPK9zQ5eawywmqHHvVt8k9rEEBYkL41O+LM/hj9oq3P8gLYwkn1GnxTU7H/ptgmrVZBVbua0ylQXxSFRudF7hbJwZgYKM7UoISiIx9E6WgXo2K7po57xAQbXz8wMssHh74i/Ey29NChJefVKtNzqlkM2h1bWjCruWXG15c1vY99OdDHQRdRj2+ohLPxdqFb0HP8xw==",
  "SigningCertURL" : "https://sns.us-east-1.amazonaws.com/SimpleNotificationService-a86cb10b4e1f29c941702d737128f7b6.pem",
  "UnsubscribeURL" : "https://sns.us-east-1.amazonaws.com/?Action=Unsubscribe&SubscriptionArn=arn:aws:sns:us-east-1:916317828206:S3toEC2Topic:30e9ea54-8ee4-4d3a-afc9-2afd26a9f1fe"
}
Will read the file docproc-invoice.txt from the bucket glsource
Line->  ******************************************************************
Line->                               Invoice
Line->  ******************************************************************
Line->  Customer-ID: sm-LK0080145
  Found Customer-ID  sm-LK0080145
Line->  Inv-ID: inv-00001
  Found Invoice-ID  inv-00001
Line->  Dated: Mar 31 2018
Line->  From: Space Mechanics Inc.
Line->  To: Starfleet Interplanatory HQ
Line->  Amount: 7650
Line->  SGST: 500
Line->  Total: 8150
Line->  InWords: Space Rupees Eight thousand one hundred fifty only
Line->  
Line->  Items
Line->  1) Matter antimatter fusion controller; 2000; 200
Line->  2) External inertial damper; 3100; 180
Line->  3) Type X phaser; 500; 35
Line->  4) 2MW Fusion reactor; 1200; 85
Line->  5) Transporter base dial; 850
  Found dated   Mar 31 2018
  Found fromcust   Space Mechanics Inc.
  Found tocust   Starfleet Interplanatory HQ
  Found amt   7650
  Found sgst   500
  Found tot   8150
  Found words   Space Rupees Eight thousand one hundred fifty only
CSV -> sm-LK0080145,inv-00001, Mar 31 2018, Space Mechanics Inc., Starfleet Interplanatory HQ, 7650, 500, 8150, Space Rupees Eight thousand one hundred fifty only

*************************************************************************
Creating table invoice
 DONE

*************************************************************************
Inserting data in the table
  Done.
Written new s3 file 59442231_sm-LK0080145_inv-00001.csv
Uploading S3 object content sm-LK0080145,inv-00001, Mar 31 2018, Space Mechanics Inc., Starfleet Interplanatory HQ, 7650, 500, 8150, Space Rupees Eight thousand one hundred fifty only
Done
[15/Nov/2020 08:13:31] "POST /sns HTTP/1.1" 200 43
Not Found: /boaform/admin/formLogin
[15/Nov/2020 09:27:16] "GET /boaform/admin/formLogin?username=admin&psd=admin HTTP/1.0" 404 2061
*********************** Incoming request *****************************   Req meta item: wsgi.version (1, 0)
  Req meta item: RUN_MAIN true
  Req meta item: SERVER_PROTOCOL HTTP/1.1
  Req meta item: SERVER_SOFTWARE WSGIServer/0.1 Python/2.7.17
  Req meta item: LC_CTYPE C.UTF-8
  Req meta item: SCRIPT_NAME 
  Req meta item: LESSOPEN | /usr/bin/lesspipe %s
  Req meta item: SSH_CLIENT 122.182.216.105 51785 22
  Req meta item: REQUEST_METHOD POST
  Req meta item: LOGNAME ubuntu
  Req meta item: USER ubuntu
  Req meta item: HOME /home/ubuntu
  Req meta item: QUERY_STRING 
  Req meta item: PATH /home/ubuntu/.virtualenvs/djangodev/bin:/home/ubuntu/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
  Req meta item: PS1 (djangodev) \[\e]0;\u@\h: \w\a\]${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ 
  Req meta item: wsgi.errors <open file '<stderr>', mode 'w' at 0x7f808ebf5270>
  Req meta item: LANG C.UTF-8
  Req meta item: TERM xterm-256color
  Req meta item: SHELL /bin/bash
  Req meta item: TZ UTC
  Req meta item: SERVER_NAME ip-172-31-50-17.ec2.internal
  Req meta item: REMOTE_ADDR 122.182.216.105
  Req meta item: XDG_DATA_DIRS /usr/local/share:/usr/share:/var/lib/snapd/desktop
  Req meta item: wsgi.url_scheme http
  Req meta item: SERVER_PORT 8080
  Req meta item: CONTENT_LENGTH 572
  Req meta item: XDG_RUNTIME_DIR /run/user/1000
  Req meta item: VIRTUAL_ENV /home/ubuntu/.virtualenvs/djangodev
  Req meta item: wsgi.input <socket._fileobject object at 0x7f8083611050>
  Req meta item: wsgi.multithread True
  Req meta item: XDG_SESSION_ID 31
  Req meta item: _ /home/ubuntu/.virtualenvs/djangodev/bin/python
  Req meta item: wsgi.file_wrapper wsgiref.util.FileWrapper
  Req meta item: SSH_CONNECTION 122.182.216.105 51785 172.31.50.17 22
  Req meta item: LESSCLOSE /usr/bin/lesspipe %s %s
  Req meta item: GATEWAY_INTERFACE CGI/1.1
  Req meta item: wsgi.run_once False
  Req meta item: SSH_TTY /dev/pts/0
  Req meta item: OLDPWD /home/ubuntu
  Req meta item: wsgi.multiprocess False
  Req meta item: SHLVL 1
  Req meta item: PWD /opt/docproc-new
  Req meta item: DJANGO_SETTINGS_MODULE docproc.settings
  Req meta item: CONTENT_TYPE text/plain
  Req meta item: MAIL /var/mail/ubuntu
  Req meta item: LS_COLORS rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=30;41:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.Z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:
  Req meta item: REMOTE_HOST 
  Req meta item: PATH_INFO /sns
POST HTTP/1.1
Content-Length: 572
Content-Type: text/plain
Headers: Postman-Token: 6e24066b-6c6c-43c1-a3fb-b4775d2e0c90
User-Agent: PostmanRuntime/7.4.0
Host: 54.146.93.185:8080
Connection: keep-alive
Cache-Control: no-cache
Accept: */*
Accept-Encoding: gzip, deflate

Body: ******************************************************************
                             Invoice
******************************************************************
Customer-ID: sm-LK0080145
Inv-ID: inv-00001
Dated: Mar 31 2018
From: Space Mechanics Inc.
To: Starfleet Interplanatory HQ
Amount: 7650
SGST: 500
Total: 8150
InWords: Space Rupees Eight thousand one hundred fifty only

Items
1) Matter antimatter fusion controller, 2000, 200
2) External inertial damper, 3100, 180
3) Type X phaser, 500, 35
4) 2MW Fusion reactor, 1200, 85
5) Transporter base dial, 850

Request method = POST
The S3 JSON is  ******************************************************************
                             Invoice
******************************************************************
Customer-ID: sm-LK0080145
Inv-ID: inv-00001
Dated: Mar 31 2018
From: Space Mechanics Inc.
To: Starfleet Interplanatory HQ
Amount: 7650
SGST: 500
Total: 8150
InWords: Space Rupees Eight thousand one hundred fifty only

Items
1) Matter antimatter fusion controller, 2000, 200
2) External inertial damper, 3100, 180
3) Type X phaser, 500, 35
4) 2MW Fusion reactor, 1200, 85
5) Transporter base dial, 850

Internal Server Error: /sns
Traceback (most recent call last):
  File "/home/ubuntu/.virtualenvs/djangodev/local/lib/python2.7/site-packages/django/core/handlers/exception.py", line 41, in inner
    response = get_response(request)
  File "/home/ubuntu/.virtualenvs/djangodev/local/lib/python2.7/site-packages/django/core/handlers/base.py", line 187, in _get_response
    response = self.process_exception_by_middleware(e, request)
  File "/home/ubuntu/.virtualenvs/djangodev/local/lib/python2.7/site-packages/django/core/handlers/base.py", line 185, in _get_response
    response = wrapped_callback(request, *callback_args, **callback_kwargs)
  File "/home/ubuntu/.virtualenvs/djangodev/local/lib/python2.7/site-packages/django/views/decorators/csrf.py", line 58, in wrapped_view
    return view_func(*args, **kwargs)
  File "/opt/docproc-new/api/views.py", line 33, in message
    process_document(request.body)
  File "/opt/docproc-new/api/views.py", line 79, in process_document
    nmsgjson = json.loads(s3json)
  File "/usr/lib/python2.7/json/__init__.py", line 339, in loads
    return _default_decoder.decode(s)
  File "/usr/lib/python2.7/json/decoder.py", line 364, in decode
    obj, end = self.raw_decode(s, idx=_w(s, 0).end())
  File "/usr/lib/python2.7/json/decoder.py", line 382, in raw_decode
    raise ValueError("No JSON object could be decoded")
ValueError: No JSON object could be decoded
[15/Nov/2020 09:41:18] "POST /sns HTTP/1.1" 500 85642
^C(djangodev) ubuntu@ip-172-31-50-17:/opt/docproc-new$ exit
logout
Connection to ec2-54-146-93-185.compute-1.amazonaws.com closed.

```