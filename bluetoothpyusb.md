## Python use pyusb to control a bluetooth dongle

### source code of pybluetooth
https://github.com/pebble/pybluetooth/blob/master/pybluetooth/pyusb_bt_sockets.py

```
# Used for composite devices:
USB_DEVICE_CLASS_MISCELLANEOUS = 0xEF
USB_DEVICE_SUB_CLASS_COMMON_CLASS = 0x02
USB_DEVICE_PROTOCOL_IAD = 0x01

USB_ENDPOINT_HCI_CMD = 0x00
USB_ENDPOINT_HCI_EVT = 0x81

pyusb's source code for ctrl_transfer
https://github.com/walac/pyusb/blob/2b09e555cb3a82d8d72e6f5264cf7c37df7e3836/usb/core.py


send
  # USB_HCI_CMD_REQUEST_PARAMS = {"bmRequestType": 0x20, "bRequest": 0x00, "wValue": 0x00, "wIndex": 0x00}
  def send(self, scapy_packet):
        data = data[1:]  # Cut off the H4 'Command' packet indicator (0x02)
        sent_len = self.pyusb_dev.ctrl_transfer(
            data_or_wLength=data, **USB_HCI_CMD_REQUEST_PARAMS)

receive
  def recv(self, x=512, timeout_secs=10.0):
        try:
            data_array = self.pyusb_dev.read(
                USB_ENDPOINT_HCI_EVT, 512, int(timeout_secs * 1000.0))
        except usb.core.USBError as e:
            if e.errno == errno.ETIMEDOUT:
                return None
            else:
                raise e

        data = ''.join([chr(c) for c in data_array])  # Ugh.. array return val
        data = "\4" + data  # Prepend H4 'Event' packet indicator
        scapy_packet = HCI_Hdr(data)

```