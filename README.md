# Setup for Windows

## Install InfluxDB

1. Download influxdb2-2.0.7-windows-amd64.zip

2. Create a folder called influxdb, in a directory of your choice and extract the contents of the upper zip file into it.

### Run InfluxDB

1. Launch Powershell with administrator privileges.
2. Move to the directory where InfluxDB is installed.
   ```sh 
   cd '.\Program Files\InfluxData\influxdb\'  ``` 
3. Run influxdb service
   ```sh
   ./influxd   ``` 
4. Open your browser and go to the following address http://localhost:8086/signin .

## Install Telegraf 

Telegraf is a plugin-driven server agent for collecting and sending metrics and events from databases, systems, and IoT sensors.

1. Launch Powershell with administrator privileges.
2. Paste and execute
   ```sh
   wget https://dl.influxdata.com/telegraf/releases/telegraf-1.19.1_windows_amd64.zip -UseBasicParsing -OutFile telegraf-1.19.1_windows_amd64.zip
   Expand-Archive .\telegraf-1.19.1_windows_amd64.zip -DestinationPath 'C:\Program Files\InfluxData\telegraf\'
   ``` 

### Install Telegraf OPC UA plugin
1. Go to  `cd .\Program Files\InfluxData\influxdb\telegraf`.
2. Create a new file and named it as `telegraf.conf`.
3. Open file `telegraf.conf` with an editor and set all the configuration for OPC UA Server through 
   https://github.com/influxdata/telegraf/blob/release-1.19/plugins/inputs/opcua/README.md instructions.
4. Save file.
5. In order to run Telegraf Service launch Powershell with administrator privileges, and go to directory 
   `cd .\Program Files\InfluxData\influxdb\telegraf`. 
6. Start service with `.\telegraf --config telegraf.conf`.


## Install Grafana

1. Go to https://grafana.com/grafana/download?platform=windows
2. Download Standalone Windows Binary.
3. Create a folder called Grafana, in a directory of your choice and extract the contents of the zip file into it.

### Run Grafana

1. Launch Powershell with administrator privileges. 
2. Go to  `cd .\Program Files\Grafana\bin`. 
3. Start service with `.\grafana-server.exe`.
