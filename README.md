# Optimal-Estimation-of-Solar-Radiation-on-Flat-Surfaces-using-Artificial-Neural-Networks
ABSTRACT

Solar Energy System uses solar energy to obtain useful energy. So, it is important to know the value of incident solar radiation in the selected place. This work proposes a method to optimally determine solar radiation using different methods such as astronomical equation and Artificial Neural Network. These methods are compared to find the better of two. As solar incident radiation is crucial for the solar energy system as it effects the energy produced and the efficiency of the system. In this work astronomical equation and Artificial Neural Network (ANN) is used to find values of global solar radiation values and are compared to the database of meteorological variables measured for ten years It is concluded from that astronomical method differs by more whereas ANN method differs only by less from database. ANN method provides better values, since it includes meteorological variables such as rate of sunshine, cloudiness, temperature, humidity and historical data of global and diffuse radiation.

Keywords: Solar Radiation, Astronomical Equation, Artificial Neural network, Solar Meters

Here the basic concepts of solar radiation, solar energy system are mentioned. This chapter introduces conventional method of solar radiation measurement and its disadvantages compared to newer method. ANN is introduced as newer method for solar prediction giving its benefits over conventional method given in chapter.

2.1. Solar radiation 
Solar energy is the cleanest and most abundant renewable energy source. Solar radiation energy emitted by the sun from a nuclear fusion reaction that creates electromagnetic energy. It consists of Direct, Diffuse and Reflected Radiation
        ◦ Direct radiation is defined as radiation that has not experienced scattering in the atmosphere.
        ◦ Diffuse radiation is solar radiation reaching earth's surface after having been scattered from the direct solar beam by molecules or suspended particles in the atmosphere.
        ◦ Reflected radiation describes sunlight that has been reflected off of non-atmospheric things such as the ground.

2.2. Solar Energy System
Solar Energy System uses solar radiation for energy production it is usually in form of electricity. These types of system use Photovoltaic (Cell, Module, Array).



The popular types of materials are crystalline and thin films, which have differences in light absorption efficiency, energy conversion efficiency, manufacturing technology and cost of production. Average energy efficiency of solar system is around 15% - 20%.
The problems related to the global warming and the degradation of the atmosphere as a consequence of using pollutants sources of energy to satisfy growing energy demand can be reduced by using renewable energy sources like Solar Energy [2].

2.3. Conventional Method
Conventionally solar radiation is measured using solar meters like pyranometer, pyrheliometer, actinograph etc. A pyranometer is a type of actinometer used for measuring solar irradiance on a planar surface and it is designed to measure the solar radiation flux density (W/m²). A pyrheliometer is an instrument for measurement of direct beam solar irradiance. Sunlight is directed onto a thermopile which converts heat to an electrical signal that can be recorded.
This measuring equipment are costly and have measurement error of around 5% - 9%. Here different components of solar radiation is measured using the following equipment 
    • Direct solar radiation is measured using pyrheliometer on a solar tracker.
    • Diffuse solar radiation is measured using pyranometer that is equipped with a shadow ring
    • Reflected solar radiation is measured using pyranometer that is placed vertically down
![image](https://github.com/user-attachments/assets/03caa120-3918-46b7-afdc-360cc3f0f53f)


METHODOLOGY
This chapter introduces different models required for the working of experiment to optimally predict of solar radiation using ANN. These models include position of sun, extraterrestrial radiation, solar radiation on surfaces and finally model of ANN. This chapter includes case study for which geographical location the experiment was done.

3.1 Model of Position of Sun
The position of the sun is defined by two variables: Altitude angle and azimuth angle.
Altitude angle: the angular height of the sun in the sky measured from the horizon, creating a plane called sun meridian
	sin𝛼= sin𝐿 sin𝛿+ cos𝐿 cos𝛿 cos𝜔 						(1)
Deviation angle is the angle formed by the sun – earth vector and the plane of the earth’s equator [4].                                                                     
![image](https://github.com/user-attachments/assets/e11f87b5-6c62-455f-9a93-9d5bb3ec5d8d)



Figure 3.1 Representation of the deviation angle [4]
Deviation angle reaches its maximum (23.45°) at the summer solstice (21 June), and its minimum (-23.45 °) at the winter solstice (December 21).


Deviation angle is given:
	                                      𝛿=23.45° sin [(2𝜋 (𝑁 −1))/365]			 	(2)
Hour angle is the angular displacement of the sun from the local point, given by:
                                                        𝜔=15° (𝐴𝑆𝑇 −12ℎ)				(3)

AST is apparent or true solar time, given by
		𝐴𝑆𝑇=𝐿𝑀𝑇+𝐸𝑜𝑇+ (4°)/ ((𝐿𝑆𝑀𝑇 −𝐿𝑂𝐷)) 		(4)
LOD is the longitude and LMST is the local standard meridian time, given by
		𝐿𝑀𝑆𝑇=15° 𝑇_𝐺𝑀𝑇 					(5)


EoT is the equation of time. The EoT is the difference between apparent and mean solar times, both taken at a given longitude at the same real instant of time:
		𝐸𝑜𝑇=9.87 sin(2𝐵) −7.53 cos𝐵 −1.5 sin𝐵 		(6)
B is given by 
		𝐵= 2𝜋/365 (𝑁 −1) 					(7)
Azimuth angle (𝜃) is defined as the angle measured from the north point until the sun meridian.
		sin𝜃= (cos𝛿 sin𝜔)/cos𝛼 				(8)
The value of the average solar constant (𝐺sc) is 1367W/𝑚^2

3.2 Extraterrestrial Solar Radiation

Solar energy is composed by extraterrestrial solar energy which is located above the atmosphere and global solar energy which is located under the atmosphere.
		𝐺𝑒𝑥𝑡= 𝐺sc (𝑅𝑎𝑣/𝑅) ^2				(9)	
R value depends on the day number, factor (𝑅_𝑎𝑣/𝑅) is given by
		

(𝑅𝑎𝑣/𝑅) = 1 + 0.0333cos (2𝜋𝑁/365)   		(10)
The extraterrestrial solar radiation unit of time falling on square meter of a surface can be given by [8]:
		𝐺𝑒𝑥𝑡= 𝐺𝑠𝑐 (1+0.0333 cos(2𝜋𝑁/365)) 		(11)




3.3 Solar radiation on surfaces

The global solar radiation (GT) is the available radiation at sea level below the Earth’s atmosphere, it has 2 components, namely, direct (beam) and diffuse solar radiation [6]
		𝐺𝑇= 𝐺B+𝐺D						(12)
  
![image](https://github.com/user-attachments/assets/13458ac7-16e7-4e9e-a943-a48091fcbecf)

Figure 3.2 Global solar radiation components on horizontal surface [5]
In addition to the direct (GB) and diffuse (GD) solar radiation, a new component called reflected solar radiation (GR) is added to form the global solar radiation incident on a tilted surface expressed by [6]:
		𝐺𝑇=𝐺𝐵+𝐺𝐷+𝐺𝑅 					(13)


![image](https://github.com/user-attachments/assets/aeac8ecf-0487-4225-9b6c-187b9ddf87a5)

Figure 3.3 Global solar radiation components on tilted surface [5]


3.4 Model of solar radiation using ANN

ANN learns from experience and examples, they have been used in a wide range of applications in pattern classification, function approximation, optimization, prediction and automatic control.
There are eight inputs and two outputs, the inputs include meteorological measurements, time specifications and measured values of global and diffused solar radiation which were used to train the network.




![image](https://github.com/user-attachments/assets/528a68ad-6f3a-40ae-94fd-cd965378206e)

Figure 3.4 ANN model for global and diffuse solar radiation prediction [1]

Feedforward Multilayer Perceptron (FFMLP) network was used here. Variables like humidity, temperature, month, day, hour affect the solar radiation [9] by including these variables the accuracy of the network increases. After 24 iterations, the predicted values of global and diffused solar radiation were obtained.
The transfer function adopted for the neurons is a logistic sigmoid function f (z), given by
		𝑓(𝑧)= 1/ (1+ 𝑒^(−𝑧)) 					(14)

