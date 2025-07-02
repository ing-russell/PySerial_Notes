# PySerial_Notes
My PySerial Notes

## Installation
In IPython Console
```
!python -m pip install pyserial
```
## Connecting ports
In IPyton Console to list ports
```
!python -m serial.tools.list_ports
```
### Classes of ports
refer to https://pyserial.readthedocs.io/en/latest/pyserial_api.html#serial.Serial.__init__

### Parameters
Params:
port – Device name or None.
baudrate (int) – Baud rate such as 9600 or 115200 etc.
bytesize – Number of data bits. Possible values: FIVEBITS, SIXBITS, SEVENBITS, EIGHTBITS
parity – Enable parity checking. Possible values: PARITY_NONE, PARITY_EVEN, PARITY_ODD PARITY_MARK, PARITY_SPACE
stopbits – Number of stop bits. Possible values: STOPBITS_ONE, STOPBITS_ONE_POINT_FIVE, STOPBITS_TWO
timeout (float) – Set a read timeout value in seconds.
xonxoff (bool) – Enable software flow control.
rtscts (bool) – Enable hardware (RTS/CTS) flow control.
dsrdtr (bool) – Enable hardware (DSR/DTR) flow control.
write_timeout (float) – Set a write timeout value in seconds.
inter_byte_timeout (float) – Inter-character timeout, None to disable (default).
exclusive (bool) – Set exclusive access mode (POSIX only). A port cannot be opened in exclusive access mode if it is already open in exclusive access mode.
Raises:	
ValueError – Will be raised when parameter are out of range, e.g. baud rate, data bits.
SerialException – In case the device can not be found or can not be configured.

#### Ello devices
baud rate = 9600
bytesize = 8
stopbits = STOPBITS_ONE
parity = PARITY_NONE

#### Kinesis devices
baud rate = 115200
bytesize = 8
stopbits = STOPBITS_ONE
parity = PARITY_NONE

### Timeout settings 
Possible values for the parameter timeout which controls the behavior of read():

timeout = None: wait forever / until requested number of bytes are received
timeout = 0: non-blocking mode, return immediately in any case, returning zero or more, up to the requested number of bytes
timeout = x: set timeout to x seconds (float allowed) returns immediately when the requested number of bytes are available, otherwise wait until the timeout expires and return all bytes that were received until then.


