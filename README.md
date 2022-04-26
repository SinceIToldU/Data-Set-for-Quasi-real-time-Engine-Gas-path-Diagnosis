# Data-Set-for-Quasi-real-time-Engine-Gas-path-Diagnosis
The Data Set used in "Quasi-real-time aero-engine gas-path diagnosis method using persistent fine-tuning with feed-forward failure data generation for tolerating lifelong distribution shift".

(Tips: There is a Chinese version below)

==Context Help==

This data set involves two engine individuals of the same type. 

During simulation, engine-to-engine variation, sensor noise and bias, performance deterioration, temperature, and flight traectories are considered.

12 gas-path failure modes are involved in the data set, with three failures for each gas-path component. 

Two of three are used in training set and testing set 1, and the rest one are used in testing set 2.

failure mode code    change in isentropic efficiency      change in flow capacity
FanFault1			              -2.33%			                          -0.93%
FanFault2 		              -2.24%			                          -1.34%
HPCFault1		                -2.69%			                          -1.08%
HPCFault2		                -2.68%			                          -1.61%
HPTFault1			              -1.85%			                          +0.74%
HPTFault2			              -1.78%			                          +1.07%
LPTFault1			              -2.77%			                          +1.11%
LPTFault2			              -2.66%			                          +1.60%

FanFaultForTesting2		      -2.40%			                          -1.00%
HPCFaultForTesting2	        -2.70%			                          -1.70%
HPTFaultForTesting2		      -1.40%			                          +2.80%
LPTFaultForTesting2		      -2.40%			                          +3.10%

In the training set, only one failure occurs in each flight. The failure is injected before takeoff. The degree of the failure does not change during the flight.
Performance deterioration measured by the exit total temperature increments of LPT(△Tt6)  is introduced in these flights.
The faulty component and failure mode code are shown on the name of the corresponding TXT file.

TXT file naming rules:
failure mode code + D + △Tt6

Testing set 1 is the same as the training set formly, but it is gleaned from another engine individual whose engine-to-engine variation and performance deterioration are unknown.

In the testing set 2, 20 hours of flight history is spliced by ten flights, with each TXT file corresponding to one flight. 
Performance deterioration related to the run time is introduced in these flights.
Only one failure occurs in the entire 20 hours. All the failures occur at the same designated time.
label: 0: fault-free, 
         1: fan failure, 
         2: HPC failure,
         3. HPT failure,
         4. LPT failure.

TXT file naming rules:
FB + flight number (+_label)

==Data Index==

The Data in the TXT file are arranged in columns in the following order:
No.	    Measurement
1	      Run Time
2	      Fan Speed 1
3	      Fan Speed 2
4	      HPC Speed 1
5	      HPC Speed 2
6	      Inlet Total Temperature
7	      Inlet Total Pressure
8	      Inlet Static Pressure
9	      Fan Exit Duct Total Temperature 1
10	    Fan Exit Duct Total Temperature 2
11	    Fan Exit Duct Total Pressure 1
12	    Fan Exit Duct Total Pressure 2
13	    HPC Exit Total Temperature 1
14	    HPC Exit Total Temperature 2
15	    HPC Exit Static Pressure 1
16	    HPC Exit Static Pressure 2
17	    Fuel Mass Flow of Main Combustor
18	    LPT Exit Total Temperature 1
19	    LPT Exit Total Temperature 2
20	    LPT Exit Total Pressure 1
21	    LPT Exit Total Pressure 2

where, XX 1 is the measured value of the sensors, XX 2 is the output value of the airborne model, and other parameters without 1 or 2 are the measured value of the sensors

==Detailed Information==
For more details about the simulation, see
1) Liao Z, Wang J, Liu J, et al. Uncertainties in gas-path diagnosis of gas turbines: Representation and impact analysis. Aerospace Science and Technology, 2021,113:106724.
2) Quasi-real-time aero-engine gas-path diagnosis method using persistent fine-tuning with feed-forward failure data generation for tolerating lifelong distribution shift (Under Review, 2020.04.30)
Your comments and citation are welcome!


==内容说明==

该数据包含两个同型号的发动机个体。
在仿真过程中，考虑了发动机个体间差异、传感器误差与噪声、性能衰退、环境温度和飞行轨迹等不确定性因素。
每次仿真过程中，海平面温度在-15℃~30℃之间随机选取。

仿真过程中涉及了12个气路故障模式，每个气路部件（风扇、高压压气机、高压涡轮、低压涡轮）各含三种故障模式。
其中的两种故障模式用于训练集和测试集A，其余一种故障模式用于测试集B。

故障模式编号       	       部件效率特性变化值      部件流量特性变化值
FanFault1			                -2.33%		              -0.93%
FanFault2 		                -2.24%		              -1.34%
HPCFault1		                  -2.69%		              -1.08%
HPCFault2		                  -2.68%		              -1.61%
HPTFault1			                -1.85%		              +0.74%
HPTFault2			                -1.78%		              +1.07%
LPTFault1			                -2.77%		              +1.11%
LPTFault2			                -2.66%		              +1.60%

FanFaultForTestingB		        -2.40%		              -1.00%
HPCFaultForTestingB	          -2.70%		              -1.70%
HPTFaultForTestingB		        -1.40%		              +2.80%
LPTFaultForTestingB		        -2.40%		              +3.10%

在训练集中，每个txt文件中仅出现一种故障，该故障在发动机运行前就已经注入，在发动机运行过程中故障程度不会改变。
运行过程中，发动机的性能衰退情况以涡轮后总温较未衰退时的升高值(△Tt6)为衡量准则，显示在了txt文件名中。
txt文件命名规则： 故障模式编号+D+△Tt6

测试集A的仿真设置与训练集类似，但运行的发动机个体为另一台个体差异与性能衰退规律未知的发动机个体。

测试集B中包含了四组20小时的飞行历史数据，每组历史数据又由10次飞行数据组成。每个txt文件对应1次飞行过程。
在仿真运行过程中，发动机的性能衰退情况设置为和发动机运行时间相关联，当运行时间为0时，发动机未发生性能衰退。
在20小时飞行历史中，仅发生了一次气路故障、四组数据中故障发生的时间点是相同的，故障模式为上述四种故障之一。
在和20小时飞行数据配套的label文件中，0：无故障，1：风扇故障，2：高压压气机故障，3.高压涡轮故障，4.低压涡轮故障
txt文件命名规则： FB + 飞行顺序编号 (+_label)

==数据索引==

txt中的数据按列顺序依次为
No.	      Measurement
1	        运行时间
2	        风扇转速 1
3	        风扇转速 2
4	        高压压气机转速 1
5	        高压压气机转速 2
6	        进气总温
7	        进气总压
8	        进气静压
9	        风扇内涵出口总温 1
10	      风扇内涵出口总温 2
11	      风扇内涵出口总压 1
12	      风扇内涵出口总压 2
13	      高压压气机出口总温 1
14	      高压压气机出口总温 2
15	      高压压气机出口总压 1
16	      高压压气机出口总压 2
17	      主燃油流量
18	      低压涡轮出口总温 1
19	      低压涡轮出口总温 2
20	      低压涡轮出口总压 1
21	      低压涡轮出口总压 2

其中，xx1为传感器测量值，xx2为机载模型的输出值，其余不含1或2的为传感器测量值

==详细信息==

数据生成及不确定性模拟方法详见论文：

1) Liao Z, Wang J, Liu J, et al. Uncertainties in gas-path diagnosis of gas turbines: Representation and impact analysis. Aerospace Science and Technology, 2021,113:106724.

2) Quasi-real-time aero-engine gas-path diagnosis method using persistent fine-tuning with feed-forward failure data generation for tolerating lifelong distribution shift (在投, 截止2020.04.30)

欢迎广大学者引用！


