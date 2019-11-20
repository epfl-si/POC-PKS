## example-ingress

### private key
openssl req -newkey rsa:2048 -nodes -keyout key.pem -x509 -days 365 -out certificate.pem

### create SSL secret
kubectl -n ic-it create secret tls star-xaas-ssl --key ./key.pem --cert ./certificate.pem

### push 
kubectl create -f web/ -f ingress.yml
