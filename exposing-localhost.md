# Exposing Localhost

## Setup a remote server 
[Google Cloud Compute](https://console.cloud.google.com/compute)

## Run server locally
`docker run -p 5678:5678 hashicorp/http-echo -text="hello world"`
- Verify server is running locally (http://localhost:5678) 

## Allow remote hosts to forwarded ports

Update file sshd_config `vi /etc/ssh/sshd_config`

```
AllowTcpForwarding yes
GatewayPorts yes
```

Restart ssh `sudo service ssh restart`

## Start remote connection

- Get ip address of remote machine `curl ifconfig.me`
- Get username for remote machine `whoami`
- Set gcloud project `gcloud config set project quickstart-1551327036490`
- Set ssh `gcloud compute config-ssh`
- Start tunnel `ssh -R 3001:localhost:5678 kushalc@kush.us-central1-a.quickstart-1551327036490`

http://\<remote ip\>:\<port\> http://34.67.91.128:3001 should be available





