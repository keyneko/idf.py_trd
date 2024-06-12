```bash
$ git clone --recursive https://github.com/espressif/esp-idf.git
$ cd esp-idf
$ git checkout v5.3
$ git submodule update --init --recursive
$ ./install.sh 
	# 如果./install.sh报错
	$ sudo rm ~/.espressif/idf-env.json 
	$ ./install.sh 

$ source '/home/keyneko/Documents/GitHub/esp-idf/export.sh'
$ idf.py create-project hello_world
$ idf.py create-component open62541

$ idf.py menuconfig 
$ idf.py --list-targets
$ idf.py set-target esp32s3
$ idf.py build
$ idf.py flash
$ idf.py monitor   # ctrl+]退出
```

# add components
```bash
$ idf.py add-dependency "espressif/led_strip^2.5.3"
$ idf.py add-dependency "espressif/asio"
$ idf.py add-dependency "espressif/esp-modbus^1.0.15"

$ idf.py create-project-from-example "espressif/led_strip^2.5.3:led_strip_rmt_ws2812"
$ idf.py create-project-from-example "espressif/asio^1.28.2:asio_chat"

$ idf.py add-dependency "espressif/iperf-cmd~0.1.1"
$ idf.py add-dependency "esp-qa/wifi-cmd~0.1.1"
$ idf.py add-dependency "esp-qa/ping-cmd~0.0.1"
```

# cmd test
```
> sta_connect Honor\ V8 88888888
> iperf -s -i 3
> iperf -c 192.168.4.1 -i 3 -t 60
> 
> wifi_mode ap
> ap_set Honor\ V8 88888888
```
