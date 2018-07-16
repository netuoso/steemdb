FROM python:3.6.6

ENV steemnode peer.proto.vit.tube

RUN apt-get update && \
    apt-get install -y git make gcc libssl-dev libgmp-dev python-dev libxml2-dev libxslt1-dev zlib1g-dev

RUN git clone https://github.com/netuoso/piston-lib/ && cd piston-lib && python3 setup.py install --user
RUN git clone https://github.com/netuoso/steem-python/ && cd steem-python && python3 setup.py install --user

RUN pip3 install pymongo scrypt

COPY . /src

CMD ["python3", "/src/sync.py"]