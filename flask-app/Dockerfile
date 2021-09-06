FROM alpine
RUN apk add py3-pip build-base python3-dev libffi-dev openssl-dev
RUN apk add nginx
RUN mkdir -p /opt/api
WORKDIR /opt/api
ADD api/requirements.txt /opt/api
RUN pip3 install --no-cache-dir -r requirements.txt
ADD api/. /opt/api
CMD ["gunicorn"  , "-b", "0.0.0.0:8000", "-w 5", "app:app"]

