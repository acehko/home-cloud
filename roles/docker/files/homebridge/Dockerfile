FROM homebridge/homebridge:2024-01-08

RUN apt-get update && \
    apt-get install -y \
      bluetooth \
      bluez \
      expect \
      netcat && \
    rm -rf /var/lib/apt/lists/*

RUN npm install --save \
    homebridge-cmdswitch2@0.2.10 \
    homebridge-dummy-thermostat@1.1.0

RUN python3 -m pip install \
      linak-controller==1.1.1

RUN sed -i 's/BLUETOOTH_ENABLED=0/BLUETOOTH_ENABLED=1/' /etc/init.d/bluetooth
RUN service bluetooth start
