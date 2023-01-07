FROM nginx:stable

COPY default.conf /etc/nginx/conf.d/default.conf
COPY ssl-params.conf /etc/nginx/snippets/ssl-params.conf
COPY nginx-selfsigned.crt /etc/ssl/certs/nginx-selfsigned.crt
COPY nginx-selfsigned.key /etc/ssl/private/nginx-selfsigned.key
COPY dhparam.pem /etc/ssl/certs/dhparam.pem 
COPY self-signed.conf /etc/nginx/snippets/self-signed.conf

EXPOSE 443
EXPOSE 80