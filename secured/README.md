# Secured CasinCoind Docker container
Generate your SSL certificate (letsencrypt) and place the certificate files in the certificate folder.

Install docker and run the following docker command in the project folder named ```secured```:

```docker build . -t casinocoind```

Start casinocoind by running the following command:

```docker run -p 0.0.0.0:4443:4443/tcp -p 0.0.0.0:5005:5005/tcp -p 0.0.0.0:17771:17771/udp -d casinocoind:latest```
