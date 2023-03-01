# Changes android_id / device_name

## pip install adbdevicechanger

### Tested against Python 3.9.15 / Windows 10 / Anaconda / BlueStacks 5.9.300.1014 N32 

Probably needs root on any device, tested only with BlueStacks.


```python

from adbdevicechanger import AdbChanger

adc = AdbChanger(
    adb_path="C:\\Users\\Gamer\\AppData\\Local\\Android\\Sdk\\platform-tools\\adb.exe",
    deviceserial="localhost:5555",
)
adc.connect_to_device()
adc.change_android_id_and_device_name(
    modelregex=".*",
    developerregex=".*",
    androidfullnameregex=".*",
    year=">1",
    month=">0",
    versionnumberaround=7.05,
)
adc.change_android_id()
adc.change_device_name(
    modelregex=".*",
    developerregex=".*",
    androidfullnameregex=".*",
    year=">1",
    month=">0",
    versionnumberaround=7.05,
)

dfframe = AdbChanger.get_random_android_cellphones(
    modelregex="Samsung.*",
    developerregex=".*",
    androidfullnameregex=".*",
    year=">2010",
    month=">0",
    versionnumberaround=9.05,
    howmany=10,
    return_list=False,
)
print(dfframe)

r"""
b'Row: 0 _id=2331, name=android_id, value=9d7f16c50ea84d99\r\n'
b'Row: 0 _id=222, name=device_name, value=Redmi 5A\r\n'
b'Row: 0 _id=2332, name=android_id, value=4ea89127afab45b4\r\n'
b'Row: 0 _id=222, name=device_name, value=Redmi 5A\r\n'
b'Row: 0 _id=2332, name=android_id, value=4ea89127afab45b4\r\n'
b'Row: 0 _id=223, name=device_name, value=ZTE Axon 7s\r\n'



                   aa_model  ...              uuid
0       Samsung Galaxy A21s  ...  c20ef8d006bd44db
1   Samsung Galaxy Z Fold 2  ...  0dfccdf0fe684649
2       Samsung Galaxy A10e  ...  ea74e780e3404b28
3       Samsung Galaxy A20s  ...  52b35c30faa249a3
4        Samsung Galaxy A10  ...  abe17cb2a0b0422b
5  Samsung Galaxy Xcover 4s  ...  c966c462ce044278
6        Samsung Galaxy A41  ...  6818973df8c1492a
7        Samsung Galaxy A70  ...  2e2fbf456043410a
8        Samsung Galaxy M02  ...  5d6b729f46184046
9        Samsung Galaxy A21  ...  4a4bd271ec60473d
[10 rows x 10 columns]

"""

```