# PSClassicGamepadDriver

Linux Driver for USB HID Playstation Classic controller

## Get Involved
I'm new to USB HID linux drivers. If you are a Linux driver veteran, please fork, contribute, or help in any way.

## Dump stream

### `sudo usbhid-dump -a <bus>:<dev> -es`

#### 2-byte buffer

         
    Byte:      A    B     C    D
    Pressed:   1111 1111  0111 1101
    Unpressed: 0000 0000  1000 0010

### Button to bit mapping:

    Triangle: B1
    Circle: B2
    Cross: B3
    Square: B4

    Start: D1
    Select: D2

    L1: A3
    L2: A1
    R1: A4
    R2: A2

    Up: C1
    Down: C2
    Left: D3
    Right: D4


## Data So far...

#### LSUSB Dump

    Bus <bus> Device <bus>: ID 054c:0cda Sony Corp. 
    Couldn't open device, some information will be missing
    Device Descriptor:
      bLength                18
      bDescriptorType         1
      bcdUSB               2.00
      bDeviceClass            0 
      bDeviceSubClass         0 
      bDeviceProtocol         0 
      bMaxPacketSize0        64
      idVendor           0x054c Sony Corp.
      idProduct          0x0cda 
      bcdDevice            1.00
      iManufacturer           1 
      iProduct                2 
      iSerial                 0 
      bNumConfigurations      1
      Configuration Descriptor:
        bLength                 9
        bDescriptorType         2
        wTotalLength           34
        bNumInterfaces          1
        bConfigurationValue     1
        iConfiguration          0 
        bmAttributes         0xa0
          (Bus Powered)
          Remote Wakeup
        MaxPower              100mA
        Interface Descriptor:
          bLength                 9
          bDescriptorType         4
          bInterfaceNumber        0
          bAlternateSetting       0
          bNumEndpoints           1
          bInterfaceClass         3 Human Interface Device
          bInterfaceSubClass      0 
          bInterfaceProtocol      0 
          iInterface              0 
            HID Device Descriptor:
              bLength                 9
              bDescriptorType        33
              bcdHID               1.11
              bCountryCode            0 Not supported
              bNumDescriptors         1
              bDescriptorType        34 Report
              wDescriptorLength      49
             Report Descriptors: 
               ** UNAVAILABLE **
          Endpoint Descriptor:
            bLength                 7
            bDescriptorType         5
            bEndpointAddress     0x86  EP 6 IN
            bmAttributes            3
              Transfer Type            Interrupt
              Synch Type               None
              Usage Type               Data
            wMaxPacketSize     0x0040  1x 64 bytes
            bInterval              10


