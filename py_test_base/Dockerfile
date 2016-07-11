# Docker : TestRunner and Unit Testing under Centos 6
FROM python:2.7

ENV LC_CTYPE=C.UTF-8
ENV LANG=C.UTF-8
ENV LANGUAGE=C.UTF-8
ENV LC_ALL=C.UTF-8

RUN apt-get update && \
    apt-get install zip -y && apt-get autoremove -y

RUN cd /tmp && wget https://bootstrap.pypa.io/ez_setup.py -O - | python

RUN cd /tmp && \
    pip install -I crcmod==1.7 && \
    pip install -I Jinja2==2.6 && \
    pip install -I pycrypto==2.6 && \
    pip install -I paramiko==1.7.7.1 && \
    pip install -I xlwt==0.7.4 && \
    pip install -I colorama==0.2.4 && \
    pip install -I reportlab==2.6 && \
    pip install -I xlutils==1.5.2 && \
    pip install -I xlrd==0.8.0 && \
    pip install -I Pyro4==4.16 && \
    pip install -I nose==1.2.1 && \
    pip install -I psycopg2

COPY ./packages/colorlog-102.zip /tmp/
RUN cd /tmp && unzip colorlog-102.zip && cd colorlog-102 && python setup.py install && cd .. && rm -rf ./colorlog-102

COPY ./packages/pydukpt-0.5.zip /tmp/
RUN cd /tmp && unzip pydukpt-0.5.zip && cd pydukpt-0.5 && python setup.py install && cd .. && rm -rf ./pydukpt-0.5

RUN cd /tmp && rm -rf * 
