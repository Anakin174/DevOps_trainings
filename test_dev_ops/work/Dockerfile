FROM ubuntu:14.04
MAINTAINER Vlad Kamerdinerov <anakin174jedi@gmail.com>
RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y -q python-all python-pip
EXPOSE 5000
ADD ./webapp/requirements.txt /tmp/requirements.txt
RUN pip install -qr /tmp/requirements.txt
ADD ./webapp /opt/webapp/
WORKDIR /opt/webapp
CMD ["python, "app.py"]