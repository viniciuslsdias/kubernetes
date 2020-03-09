FROM alpine:3.11.3

#install curl
RUN apk add curl

#install kube control
RUN curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl \
&& chmod +x kubectl \
&& mv kubectl /usr/local/bin/

#install python
RUN apk add python

#install aws cli
RUN curl "https://s3.amazonaws.com/aws-cli/awscli-bundle.zip" -o "awscli-bundle.zip" \
&& unzip awscli-bundle.zip \
&& ./awscli-bundle/install -b ~/bin/aws \
&& ln -s /root/.local/lib/aws/bin/aws /usr/local/bin/

#clean aws cli installation files
RUN rm -f  awscli-bundle.zip \
&& rm -fr awscli-bundle

#unistall curl
RUN apk --purge -v del curl

#clean cache
RUN rm -fr /var/cache/apk/*
