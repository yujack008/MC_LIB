# Motor-FOC

## 处于测试阶段，目前可以切闭环，但是运行过程中会出现一顿一顿的情况。
单片机: 基于HC32-F003J8TA(ARM Cortex-M0+内核) </br>
开发平台：Keil5  </br>
电流采样：***双电阻采样***</br>
角度估算：***滑膜估算器+反正切*** </br>
项目介绍：本项目通过双电阻采样下管对地电流。采样时刻：***下管导通中间时刻采样***提高电流准确性。通过滑膜估算器对电流的估算，得到反电动势，滤波后反正切获取估算角。 </br>
Tip：不同电机，需要调整参数：相电感，相电阻，工作电压，最大电流。启动的过零点检测延迟。 </br>
问题总结：之前一直困扰我的切入闭环PI速度环问题，其实不是PI的锅，是因为相电流采样电路里的电容太大导致的信号延迟太高，使得估算角度的延时也变高了，通过加大延时就转起来了。
