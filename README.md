# Tpa3221_classD_Amp
## For 8 Ω speaker
Mode = master <br>
Modulation Mode : AD Mode<br>
Freq = 600khz <br>
Gain = 18dB  ( Vout/Vin = 8 ) <br>
Functional Mode: Stereo BTL <br>
LC Fliter : 10uH + 680nF *(approx 61kHz)* 20kHz -> Gain≈+0.5dB@8Ω<br>
*Recommed Fliter capacitor use Metalized Film(like CCB)*<br><br>
![Topview](https://raw.githubusercontent.com/huhu6608/Tpa3221_classD_Amp/main/asserts/Top.jpg)
*<p align="center">v1.0_Top view</p>*<br>

![Bottomview](https://raw.githubusercontent.com/huhu6608/Tpa3221_classD_Amp/main/asserts/Bottom.jpg)
*<p align="center">v1.0_Bottom view</p>*

# Contents
1.[输入信号](#输入信号)<br>
2.[上电及关机](#上电及关机)<br>
3.[Tips](#Tips)<br>
4.[Version](#Version)<br>











## 输入信号 
1.如果是单端输入首先建议增加单端转平衡电路Click [here](https://github.com/huhu6608/Audio_SE_to_Diff).<br>
2.单端直接输入（无电位器音量调节），此时为伪差分输入，应做好阻抗匹配（*R4、R5*）。<br>
3.单端输入直接加电位器进行音量调节似乎也未见异常情况。<br>
## 上电及关机
本设计无上电及掉电检测，所以关机后会造成仍播放声音（大约5s），可以增加EVM中的掉电检测（电源指示灯仍会15s后完全熄灭）。<br>
## Tips
1.上电之前应检测所有引脚是否焊接到位，可以分为两个象限，先测芯片右侧功率输出端，再测左侧模拟、数字部分。左侧一些接地引脚务必都要检查，他们分别管理不同功能，比如***RESET***与***CUMTE***可能有着不同的接地引脚，但是他们如果有任何一个没有上电都会造成芯片无法工作。<br>
2.上电后应先测试***RESET***与***CUMTE***是否为高电平，***RESET***引脚大概为4.8v左右，***CUMTE***引脚为5v左右。这个很重要，是判断芯片是否开始正常工作的依据。<br>
3.单端输入应当短路*TestPad*。<br>
4.建议输入电压在*18v~20v*如果更高电压应当修改*R6*改变增益来获得更大输出功率，如果是伪差分直接输入应重新进行阻抗匹配。同样输入电容也应当重新选值，使得低频截止不至于过高。<br>
5.输出*LC*滤波电容应选用金属膜电容（比如CCB），本设计使用680nF电容在使用8Ω喇叭输出时高频可能会有稍许衰减，可以增加到1μF，由于喇叭阻抗以及*LC*滤波器共同作用高频部分可能会有稍许提高。<br>
6.如果用仪器测试（用普通信号发生器单端输入），不应使信号发生器与示波器共地，这时H桥与地形成通路这将造成芯片损坏。<br>

## Version
**V1.0**<br>
1.reset等接口未进行标注。<br>
2.bottom输出未进行标注。<br>
3.*R1*位置不够合理<br>
**V1.1**<br>
1.更改了所有标注。<br>
2.改变了*R1*位置。<br>