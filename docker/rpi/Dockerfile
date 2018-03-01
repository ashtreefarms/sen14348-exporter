FROM resin/raspberry-pi-python:3-slim
LABEL maintainer="jake.krog@gmail.com"

WORKDIR /tmp/
RUN apt-get update -y && apt-get install -y git \
    && git clone https://github.com/adafruit/Adafruit_Python_BME280.git \
    && cd Adafruit_Python_BME280 && python setup.py install

WORKDIR /usr/src/app
COPY . .
RUN pip install -r requirements.txt && python setup.py install

EXPOSE 9502
ENTRYPOINT ["sen14348_exporter"]
