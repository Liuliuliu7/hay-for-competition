`pyserial`
:luc_download:**install**: `pip install pyserial` or `conda install -c conda-forge pyserial`.
> This module encapsulates the access for the serial port
> [python库之pyserial用法](https://blog.csdn.net/Electrical_IT/article/details/107201561)

`struct`
> Interpret bytes as packed binary data
> [(Python标准库—struct模块)](https://blog.csdn.net/L_zzwwen/article/details/100068669)

```python
import struct
# < --> litter-ending, B --> interger
struct.pack('<B', servo_id)
struct.unpack('<B', param_bytes)
```


