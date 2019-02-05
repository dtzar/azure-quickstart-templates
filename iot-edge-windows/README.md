# Deploy a Windows Server VM and create an IoT Edge device

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2Fiot-edge-windows%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>
<a href="https://portal.azure.us/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2Fiot-edge-windows%2Fazuredeploy.json" target="_blank">
<img src="https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazuregov.png"
</a>
<a href="http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2Fiot-edge-windows%2Fazuredeploy.json" target="_blank">
    <img src="http://armviz.io/visualizebutton.png"/>
</a>

This template deploys Windows Server 2019 Datacenter with Containers and automatically creates an IoT Edge device and connects with its device in IoT Hub via a PowerShell script.

If there is no IoT Edge device registered with the IoT Hub, replace `<myIoTHub>` with the existing IoTHub value and then create the virtual device:

```shell
az iot hub device-identity create --hub-name <myIoTHub> --device-id myTestDevice --edge-enabled
```

To get the secure connection string for the IoT Edge device to pass into the `IoTHubEdgeDeviceCS` parameter, replace `<myIoTHub>` and execute:

```shell
az iot hub device-identity show-connection-string --device-id myTestDevice --hub-name <myIoTHub> --query cs -o tsv
```