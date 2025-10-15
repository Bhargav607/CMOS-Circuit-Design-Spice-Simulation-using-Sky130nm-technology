# CMOS-Circuit-Design-Spice-Simulation-using-Sky130nm-technology
CMOS-Circuit-Design-Spice-Simulation-using-Sky130nm-technology

## Table Of Contents
- [NgspiceSky130-Day1-Basics of NMOS Drain Current(Id) vs Drain-to-source Voltage(Vds)](#NgspiceSky130-Day1-Basics-of-NMOS-Drain-Current(Id)-vs-Drain-to-source-Voltage(Vds))
  - [Introduction to Circuit Design and Spice Simulations](#Introduction-to-Circuit-Design-and-Spice-Simulations)
    - [L1 Why do we need SPICE simulations?](#L1-Why-do-we-need-SPICE-simulations?)
    - [L2 Introduction to basic element in circuit design-NMOS](#L2-Introduction-to-basic-element-in-circuit-design-NMOS)
    - [L3 Strong inversion and threshold voltage](#L3-Strong-inversion-and-threshold-voltage)
    - [L4 Threshold voltage with positive substrate potential](#L4-Threshold-voltage-with-positive-substrate-potential)
  - [NMOS resistive region and Saturation region of operation](#NMOS-resistive-region-and-Saturation-region-of-operation)
    - [L1 Resistive region of operation with small drain-source voltage](#L1-Resistive-region-of-operation-with-small-drain-source-voltage)
    - [L2 Drift current theory](#L2-Drift-current-theory)
    - [L3 Drain current model for Linear region of operation](#L3-Drain-current-model-for-Linear-region-of-operation)
    - [L4 SPICE conclusion to resistive operation](#L4-SPICE-conclusion-to-resistive-operation)
    - [L5 Pinch-off region condition](#L5-Pinch-off-region-condition)
    - [L6 Drain current model for saturation region of operation](#L6-Drain-current-model-for-saturation-region-of-operation)
  - [Introduction to SPICE](#Introduction-to-SPICE)
    - [L1 Basic SPICE setup](#L1-Basic-SPICE-setup)
    - [L2 Circuit description in SPICE syntax](#L2-Circuit-description-in-SPICE-syntax)
    - [L3 Define Technology parameters](#L3-Define-Technology-parameters)
    - [L4 First SPICE simulation](#L4-First-SPICE-simulation)
    - [L5 SPICE lab with Sky130 models](#L5-SPICE-lab-with-Sky130-models)
- [NgspiceSky130-Day2-Velocity saturation and basics of CMOS inverter VTC](#NgspiceSky130-Day2-Velocity-saturation-and-basics-of-CMOS-inverter-VTC)
  - [SPICE simulation for lower nodes and velocity saturation effect](#SPICE-simulation-for-lower-nodes-and-velocity-saturation-effect)
    - [L1 SPICE simulation for lower nodes](#L1-SPICE-simulation-for-lower-nodes)
    - [L2 Drain current vs gate voltage for long and short channel device](#L2-Drain-current-vs-gate-voltage-for-long-and-short-channel-device)
    - [L3 Velocity saturation at lower and higher electric fields](#L3-Velocity-saturation-at-lower-and-higher-electric-fields)
    - [L4 Velocity saturation drain current model](#L4-Velocity-saturation-drain-current-model)
    - [L5 Labs Sky130 Id-Vgs](#L5-Labs-Sky130-Id-Vgs)
    - [L6 Labs Sky130 Vt](#L6-Labs-Sky130-Vt)
  - [CMOS voltage transfer characteristics (VTC)](#CMOS-voltage-transfer-characteristics-(VTC))
    - [L1 MOSFET as a switch](#L1-MOSFET-as-a-switch)
    - [L2 Introduction to standard MOS voltage current parameters](#L2-Introduction-to-standard-MOS-voltage-current-parameters)
    - [L3 PMOS/NMOS drain current vs drain voltage](#L3-PMOS/NMOS-drain-current-vs-drain-voltage)
    - [L4 Step1- Convert PMOS gate-source-voltage to Vin](#L4-Step1--Convert-PMOS-gate-source-voltage-to-Vin)
    - [L5 Step2 & Step3- Convert PMOS and NMOS drain-source-voltage to Vout](#L5-Step2-&-Step3--Convert-PMOS-and-NMOS-drain-source-voltage-to-Vout)
    - [L6 Step4- Merge PMOS-NMOS load curves and plot VTC](#L6-Step4--Merge-PMOS-NMOS-load-curves-and-plot-VTC)
- [NgspiceSky130-Day3-CMOS switching threshold and dynamic simulations](#NgspiceSky130-Day3-CMOS-switching-threshold-and-dynamic-simulations)
  - [Voltage transfer characteristics-SPICE simulations](#Voltage-transfer-characteristics-SPICE-simulations)
    - [L1 SPICE deck creation for CMOS inverter](#L1-SPICE-deck-creation-for-CMOS-inverter)
    - [L2 SPICE simulation for CMOS inverter](#L2-SPICE-simulation-for-CMOS-inverter)
    - [L3 Labs Sky130 SPICE simulation for CMOS](#L3-Labs-Sky130-SPICE-simulation-for-CMOS)
  - [Static behaviour evaluation-CMOS inverter robustness-Switching Threshold](#Static-behaviour-evaluation-CMOS-inverter-robustness-Switching-Threshold)
    - [L1 Switching Threshold, Vm](#L1-Switching-Threshold,-Vm)
    - [L2 Analytical expression of Vm as a function of (W/L)n and (W/L)p](#L2-Analytical-expression-of-Vm-as-a-function-of-(W/L)n-and-(W/L)p)
    - [L3 Analytical expression of (W/L)n and (W/L)p as a function of Vm](#L3-Analytical-expression-of-(W/L)n-and-(W/L)p-as-a-function-of-Vm)
    - [L4 Static and Dynamic simulation of CMOS inverter](#L4-Static-and-Dynamic-simulation-of-CMOS-inverter)
    - [L5 Static and Dynamic simulation of CMOS inverter with increased PMOS width](#L5-Static-and-Dynamic-simulation-of-CMOS-inverter-with-increased-PMOS-width)
    - [L6 Applications of CMOS inverter in clock network and STA](#L6-Applications-of-CMOS-inverter-in-clock-network-and-STA)
- [NgspiceSky130-Day4-CMOS Noise Margin robustness evaluation](#NgspiceSky130-Day4-CMOS-Noise-Margin-robustness-evaluation)
  - [Static behaviour evaluation-CMOS inverter robustness-Noise Margin](#Static-behaviour-evaluation-CMOS-inverter-robustness-Noise-Margin)
    - [L1 Introduction to Noise Margin](#L1-Introduction-to-Noise-Margin)
    - [L2 Noise Margin voltage paramters](#L2-Noise-Margin-voltage-paramters)
    - [L3 Noise margin equation and summary](#L3-Noise-margin-equation-and-summary)
    - [L4 Noise margin variation with respect to PMOS width](#L4-Noise-margin-variation-with-respect-to-PMOS-width)
    - [L5 Sky130 Noise margin labs](#L5-Sky130-Noise-margin-labs)
- [NgspiceSky130-Day5-CMOS power supply and device variation robustness evaluation](#NgspiceSky130-Day5-CMOS-power-supply-and-device-variation-robustness-evaluation)
  - [Static behaviour evaluation-CMOS inverter robustness-Power supply variation](#Static-behaviour-evaluation-CMOS-inverter-robustness-Power-supply-variation)
    - [L1 Smart SPICE simulations for power supply variations](#L1-Smart-SPICE-simulations-for-power-supply-variations)
    - [L2 Advantages and disadvantages using low supply voltage](#L2-Advantages-and-disadvantages-using-low-supply-voltage)
    - [L3 Sky130 Supply variation Labs](#L3-Sky130-Supply-variation-Labs)
  - [Static behaviour evaluation-CMOS inverter robustness-Device variation](#Static-behaviour-evaluation-CMOS-inverter-robustness-Device-variation)
    - [L1 Sources of variation - Etching process](#L1-Sources-of-variation---Etching-process)
    - [L2 Sources of variation - Oxide thickness](#L2-Sources-of-variation---Oxide-thickness)
    - [L3 Smart SPICE simulation for device variations](#L3-Smart-SPICE-simulation-for-device-variations)
    - [L4 Conclusion](#L4-Conclusion)
    - [L5 Sky130 device variations labs](#L5-Sky130-device-variations-labs)

# NgspiceSky130-Day1-Basics of NMOS Drain Current(Id) vs Drain-to-source Voltage(Vds)

## Introduction to Circuit Design and Spice Simulations

### L1 Why do we need SPICE simulations?
A circuit design includes PMOS and NMOS tied together in such a fashion that they result into logic gates such as NAND, NOR, OR, AND etc.</br>

<img width="542" height="526" alt="image" src="https://github.com/user-attachments/assets/bf9b9eed-3cf4-41be-bcfe-8b3ea7eadcb0" />

The above inverter will have the following charactersitics, we will do the SPICE simulations to find the delay and so we will get the W/L ratio of the particular transistor.</br>

<img width="965" height="695" alt="image" src="https://github.com/user-attachments/assets/e2264a62-e4b1-4506-bb0f-eded09d303f3" />

**WHy do we need SPICE?**</br>
The clock Tree synthesis, crosstalks, and timing are built on SPICE (Simulation Program with Integrated Circuit Emphasis), without SPICE there won't be delays and if there are no delays physical design flow, crosstalk won't make any sense.</br>

Let us say we have done some Clock Tree Synthesis of the circuit shown below with bufffers with different capacitive load at the output.</br>

<img width="1206" height="392" alt="image" src="https://github.com/user-attachments/assets/a0dbe0ed-6981-4966-8d1d-7bf4d223ef61" />

After the SPICE simulation we get a "Delay Table", which includes input slew and output load. The intersection value of Input slew and Output load is considered as Delay. Delay tables for both level 1 and level 2 buffers have been shown. This is calculated by circuit design and simulation</br>

<img width="1410" height="668" alt="image" src="https://github.com/user-attachments/assets/422a8a28-f4e6-469a-97d4-535f02762e3d" />

The source of the above Delay Tables comes from circuit design using SPICE simulations. SPICE simulations involves characterisation of any CMOS logic.</br>

### L2 Introduction to basic element in circuit design-NMOS
An NMOS transistor consist of P-type substrate, heavily doped with n+ region. There is an isolated region which isolates the transistor from other transistors. The n+regions are Source and Drain. Above itthere is an oxide layer, and top of it is metal deposition which is the GAte termianal.</br>

<img width="1195" height="507" alt="image" src="https://github.com/user-attachments/assets/fafb4e04-8d70-42dd-bae3-7570c38be028" />

**Threshold Voltage**
This is a very important term, all the characterisation depends on threshold voltage.</br>
At first we will keep the Vgs=0, means source and drain terminal both are grounded. Body is also ground. P-substrate and n+ act as PN junction diode and as there is no potential so there is a high resistance. No channel formation is there.</br>

<img width="1322" height="528" alt="image" src="https://github.com/user-attachments/assets/8e2fee4c-8616-4886-859c-d6c08d166541" />

Now we will apply a positive potential; Vgs>0. We will see gate is now positively charged and due to this there will be Accumulation of negative charges at the surface of substrate.</br>

<img width="1345" height="555" alt="image" src="https://github.com/user-attachments/assets/ef79f61f-5540-4ffb-aec8-06fa9354759a" />

### L3 Strong inversion and threshold voltage
Due to Accumulation of negatuve charges, there will be formation of Depletion Region, depleting of it's majority carriers i.e positive carriers here.</br>

<img width="831" height="402" alt="image" src="https://github.com/user-attachments/assets/335a3525-699e-4c66-8161-2201df2b9070" />

Now we will increase the Gate voltage further, we will see that the positive charge carriers will be repelled and there will be increase of Depletion Width. On further increase of Gate voltage we will reach at a point where the surface gets inverted into an n-type material, this is called "Surface Inversion" or "Strong Inversion". The gate voltage of Vgs voltage where Strong Inversion happens is called "Threshold Voltage".</br>

<img width="1332" height="551" alt="image" src="https://github.com/user-attachments/assets/03776359-fd17-4e04-9fd5-9212422217df" />

What will happen if we further increase Vgs? As there are no more negative charges that will be attracted towards the positive Vgs, The negative charges from n+ region will get attracted and so there will be a formation of channel at the surface.</br>

<img width="1358" height="573" alt="image" src="https://github.com/user-attachments/assets/f8c47353-dbf7-4026-b4d9-89ebff6cd24d" />

<img width="1350" height="618" alt="image" src="https://github.com/user-attachments/assets/183a52c0-755d-43c6-9731-9043b047e679" />

Now there is a possibility of current from Source to Drain. The channel has bridged the gap between source to drain regions. But as there is no Drain voltage so the elctrons will not move, this is "Cut Off Region" now.</br>

We will see what happens when we change the potential of Body terminal.</br>

<img width="1311" height="532" alt="image" src="https://github.com/user-attachments/assets/0aa83b1f-12c2-4765-bd3f-caa35daac877" />

There will be increase in depletion region between source and body terminal. </br>

<img width="1283" height="607" alt="image" src="https://github.com/user-attachments/assets/1dd9f64e-5345-4dc9-98b2-6dcde19765ef" />

### L4 Threshold voltage with positive substrate potential
If we increase Vgs, we will see that the depletion region increase in both the cases. But, in second case as there is Vsb +ve, few charges from channel will be pulled towards the source.</br>

<img width="1247" height="617" alt="image" src="https://github.com/user-attachments/assets/65d128ea-03af-4dd4-af13-28b261e0fe66" />

Due to this the surface inversion will be slower in second case. Therefore some extra potential has to be apllied in second case to create inversion.</br>

<img width="1356" height="658" alt="image" src="https://github.com/user-attachments/assets/98b3483c-2c33-4244-b96d-6098ee9b0163" />

<img width="632" height="235" alt="image" src="https://github.com/user-attachments/assets/8025a009-e2dd-4e83-a4d6-c1725668e6fc" />

The parameters such as Gamma comes from foundaries after simulation of which in SPICE we get the value for Vt (Threshold Voltage).</br>

<img width="1327" height="643" alt="image" src="https://github.com/user-attachments/assets/8955fdc9-1230-4562-b513-4eca06eb5d3c" />

## NMOS resistive region and Saturation region of operation

### L1 Resistive region of operation with small drain-source voltage
Previously, we saw Cut Off region operation, now we will see the "Resistive region"/"Linear Region" of operation by applying Drain-source voltage.
If we keep on increasing the Gate-source voltage, the channel width keeps on increasing.</br>

<img width="1305" height="508" alt="image" src="https://github.com/user-attachments/assets/29f349a8-c77e-4d13-a323-82b1fa6bfb74" />

This shows that the net Induced charges is propotional to (Vgs-Vt). Now let's apply very small Vds at start. And keep Vt=0.45V, Vgs also small initially.</br>

<img width="1317" height="567" alt="image" src="https://github.com/user-attachments/assets/aed1572f-fd2b-492d-82ca-bd1ce4a94b1e" />

We can see that the source is grounded and Drain is at some potential, so there will be a voltage gradient accross the channel.</br>

<img width="1318" height="577" alt="image" src="https://github.com/user-attachments/assets/bf52a8c7-5553-4c74-888c-cdb43b09e3bc" />

Also, the Effective channel length is much lesser than the original channel length.</br>

<img width="797" height="510" alt="image" src="https://github.com/user-attachments/assets/c35a777b-b625-495c-bb37-9f92dfd92a64" />

Here, y axis represents the width of transistor and x axis is the voltage across the channel.</br>
On applying Vds, every point on x axis will vary w.r.t to Vgs-V(x), this will decide the current equation.</br>

<img width="817" height="558" alt="image" src="https://github.com/user-attachments/assets/a472661e-b9bd-4cfb-8437-ea5be2474fe2" />

### L2 Drift current theory
We know the effective channel voltage will vary w.r.t x, for example at x=0, Vgs=1V and V(x)=0, So the Vgs-Vx=1V. At x=Vds=0.05V, Vgs-Vx=0.95V. Now if we see the induced chagre equation, it is proportional to the effective channel voltage.</br>

<img width="411" height="150" alt="image" src="https://github.com/user-attachments/assets/f303fe6e-388f-4395-9650-e7121cd5aff4" />

<img width="390" height="451" alt="image" src="https://github.com/user-attachments/assets/14f8c404-0d02-4d21-8d67-b20ff1801eae" />

There are two types of currents; Dift and Diffusion current, Here there is Drift current as there is potential difference across the channel.</br>

<img width="1285" height="618" alt="image" src="https://github.com/user-attachments/assets/e1ba1c63-b342-4377-9fe8-1a2e58c93e02" />

To get the drain current, we will see the top view of transistor.</br>

<img width="1311" height="687" alt="image" src="https://github.com/user-attachments/assets/6c473806-a163-4120-974a-73e11da97839" />

### L3 Drain current model for Linear region of operation
As there is change of voltage across the channel length, this will result in change of velocity which is a function of mobility and electrci field.</br>

<img width="448" height="651" alt="image" src="https://github.com/user-attachments/assets/6518460a-1e4c-481f-8341-d99a1fa9a376" />

We will integrate the above equation, where limits of dV will be from 0 to Vds and limits of dx will be from 0 to L.</br>

<img width="442" height="428" alt="image" src="https://github.com/user-attachments/assets/382f07af-71b5-4f00-894d-bdab05e92d0e" />

<img width="377" height="48" alt="image" src="https://github.com/user-attachments/assets/f6f5158c-850f-4272-b381-0b57dc30e7a9" />

Here, Cox, W/L, Vgs, un and Vt are the 'technology parameters', we will simulate usinf SPICE and find out the characteristics.</br>

<img width="387" height="211" alt="image" src="https://github.com/user-attachments/assets/ee457e12-6af7-4389-a11a-036ba5a4b652" />

But, here we cannot say that it is in Linear region, since the Drain current is the quadratic function of Vds. We will calculate the Id with the given values.</br>

<img width="708" height="432" alt="image" src="https://github.com/user-attachments/assets/853ed5fa-0257-4a73-91dd-09007f16d273" />

When (Vgs-Vt)>=Vds, It is in "Linear region".</br>

<img width="683" height="443" alt="image" src="https://github.com/user-attachments/assets/bdfa5383-5b3b-452f-b437-0768814f2551" />

### L4 SPICE conclusion to resistive operation
We need to find the impact of Vgs and Vds on the drain current equation. We will consider different values of Vgs and Vds. If we consider different values of Vgs, under what condition the device will remain in Linear region depends on (Vgs-Vt) should be greater than Vds.</br>

<img width="591" height="172" alt="image" src="https://github.com/user-attachments/assets/d9735c9f-3a26-49aa-bc9b-62e64d65babe" />

Now the main question arises, How do we calculate Id for different values of 'Vgs' and at every value of 'Vgs', sweep Vds till (Vgs-Vt) using linear equation for Id?</br>
For this we need to do SPICE simulations.</br>

### L5 Pinch-off region condition
There is also a Region of operation when Drain-source voltage exceeds the value (Vgs-Vt), the region of operation is called "Saturation Region".
We know the channel voltage is Vgs-Vds. Now, we will increase the Vds.</br>

<img width="1367" height="625" alt="image" src="https://github.com/user-attachments/assets/d29ecff9-3641-49c7-9348-fa7537ff7118" />

When Vgs-Vds is greater than Vt, there will be a conducting channel.</br>
When Vgs-Vds is equal to Vt, we will see at drain side, just Inversion has happened as it is equal to Vt, so channel will start disappearing at drain side.</br>

<img width="1380" height="611" alt="image" src="https://github.com/user-attachments/assets/b51e39ef-093f-463d-8faa-7c6bb23cc68d" />
<img width="1352" height="621" alt="image" src="https://github.com/user-attachments/assets/8d325d80-10d4-47e3-aed0-2caaf0715a36" />

Now when the channel starts to disappear, is termed as "Pinch off region"</br>

<img width="1492" height="602" alt="image" src="https://github.com/user-attachments/assets/40146460-641e-4f89-a950-acebeba103e3" />

When Vgs-Vds<Vt, we will not see any channel present at drain side.</br>

<img width="1310" height="582" alt="image" src="https://github.com/user-attachments/assets/e62baac0-53e1-4c61-a9d6-e26a0a4b8ec1" />

This condition is termed as "Saturation region", when the mosfet is saturated and cannot do anything further.</br>

<img width="391" height="102" alt="image" src="https://github.com/user-attachments/assets/4c0aca6a-e230-47d1-9e30-9416785487be" />

### L6 Drain current model for saturation region of operation
In saturation region, the channel voltage will remain constant as 'Vgs-Vt', and the drain current will not depend on Vds.</br>
To get drain current equation in saturation region we will replace Vds as Vgs-Vt.</br>

<img width="467" height="360" alt="image" src="https://github.com/user-attachments/assets/3df0adef-9616-499c-97de-477da403178b" />

We can now see that according to the equation, the mosfet acts as perfect current source. But this is not true, when we increase Vds we will that Depletion region at drain increases and so channel length further reduces.Therefore, we see a slight dependency of Vds over Id</br>

<img width="1476" height="586" alt="image" src="https://github.com/user-attachments/assets/899bf2cb-f752-43ad-8750-5fc9d6b62f50" />

This is called "Channel Length Modulation".</br>

<img width="876" height="168" alt="image" src="https://github.com/user-attachments/assets/b3d388c1-7074-49c9-a019-7d0ff212271f" />

## Introduction to SPICE

### L1 Basic SPICE setup
First let us look into the SPICE setup.</br>

<img width="1412" height="611" alt="image" src="https://github.com/user-attachments/assets/5872cd9a-70d1-46cf-9fe4-f5247f8d3415" />

Some parameters are constant, and directly coming from the foundaries we don't have to derive them. These are circiled in yellow.</br>

<img width="1313" height="591" alt="image" src="https://github.com/user-attachments/assets/c7f8c503-a596-40a7-85e8-b00b1eef4cf9" />

<img width="922" height="536" alt="image" src="https://github.com/user-attachments/assets/260175cb-7abc-4fc6-a332-6b73b7954cae" />

So, when we feed the SPICE model parameters and SPICE netlist intp the SPICE software, we get the device characteristics in terms of Id vs Vds with different values of Vgs.</br>

**SPICE Netlist**
We need to feed the device into SPICE engine in certain manner, the circuit equivalent of given mosfet is as shown below. </br>

<img width="1262" height="585" alt="image" src="https://github.com/user-attachments/assets/ec870ea4-f7ce-4e99-939a-d6e8646c499e" />

### L2 Circuit description in SPICE syntax
Now we will write the syntax for this particular circuit in SPICE netlist. To do that we need to follow some steps-
* **Define Nodes**
  
  <img width="653" height="410" alt="image" src="https://github.com/user-attachments/assets/726a94e6-1333-41dc-a4c0-d9c766b00f9b" />

* **Give names to the node**
* **Write the code**
  `since modfet has 4 terminals, it is lying between 4 different nodes, similarly resistor is lying between 2 nodes.`

<img width="1307" height="418" alt="image" src="https://github.com/user-attachments/assets/fe360627-afb9-41d7-917d-95b7ac8ca6b7" />
<img width="1211" height="371" alt="image" src="https://github.com/user-attachments/assets/5d8f624b-296a-499a-9cc2-c9fd0946fb52" />
<img width="1213" height="412" alt="image" src="https://github.com/user-attachments/assets/c7d30d08-94c4-4891-95b3-4fc8c95fa3c9" />
<img width="1132" height="381" alt="image" src="https://github.com/user-attachments/assets/b9dad3c6-2cc6-48a5-9409-a7eb90f39301" />
<img width="1197" height="385" alt="image" src="https://github.com/user-attachments/assets/e091f59b-d7b8-4913-9ee3-0a2cc5d324f0" />

The fashion in which it is written is "Drain", "Gate", "Source", and "Substrate" (DGSS).</br>

<img width="1252" height="471" alt="image" src="https://github.com/user-attachments/assets/f9599207-d326-4da5-b92b-53d80a85c4cb" />
<img width="1172" height="406" alt="image" src="https://github.com/user-attachments/assets/15ce1ea6-b8d3-47f6-9ef9-978ddd83bbc6" />
<img width="1242" height="402" alt="image" src="https://github.com/user-attachments/assets/36660836-b886-4c2e-9649-d13863d65f7f" />

this is a long channel mosfet.

Similarly we can write for Resistor.</br>
<img width="1263" height="416" alt="image" src="https://github.com/user-attachments/assets/880832b5-5f1b-49f3-9c01-25ef9bdc55c4" />
<img width="1247" height="463" alt="image" src="https://github.com/user-attachments/assets/1d36164e-cf12-49e3-84b5-8f2928f4a8b9" />
<img width="1345" height="370" alt="image" src="https://github.com/user-attachments/assets/fb1e6449-cf20-48d7-9888-eadc40c5319c" />
<img width="1342" height="422" alt="image" src="https://github.com/user-attachments/assets/53c100fd-845e-474d-b3a3-9a53bfc0ee45" />
<img width="637" height="308" alt="image" src="https://github.com/user-attachments/assets/6498b3c6-8eda-40ee-adf7-c9a6e332675f" />

### L3 Define Technology parameters
Now we will look for model of this particular NMOS. For this we have model paramters, and it becomes easy to model from the parameters. That is where the technology file comes into picture. The models for the name NMOs will be found in file which has the attribute of the similar name.</br>

<img width="1312" height="592" alt="image" src="https://github.com/user-attachments/assets/4fa6b7c5-61d6-45f7-ba68-ad15a67426eb" />

Inside the brackets, technology paramteters will exist. Similarly for pmos also.</br>

<img width="542" height="107" alt="image" src="https://github.com/user-attachments/assets/cbef3e32-99d7-4998-9957-e89c4ba96c57" />

Now, we just plug in this packaged file in `.mod` file and call this file in top level SPICE netlist.</br>

<img width="553" height="475" alt="image" src="https://github.com/user-attachments/assets/f7752179-bfcb-420b-a1df-0af1a648be2c" />
<img width="603" height="197" alt="image" src="https://github.com/user-attachments/assets/23ce231b-f774-437b-ae5a-d3f0836d0a57" />

<img width="635" height="257" alt="image" src="https://github.com/user-attachments/assets/163cf011-37b0-450d-b7d4-4a915bc70653" />

In the above image, the highlighted part is comment in SPICE.</br>
Now, we need to sweep the Vgs and Vds for SPICE simulations.</br>

### L4 First SPICE simulation
* Open Virtual box
* Type `cd`
* `git clone https://github.com/kunalg123/sky130CircuitDesignWorkshop.git`
  <img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/414d1bb8-13a1-4726-92cb-06ea15ed382f" />

  inside the `sky130_fd_pr` directory we will see cells, models and tech files.</br>

  <img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/be98370e-7126-4eb4-959d-ce8d40133e9a" />

  Inside the `cells` files we will see `nfet` and `pfet` cells, these cells we will be using.</br>

  Inside `nfet` we will see spice libraries at different corners, we will select one such typical corner.</br>
  <img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/99aa0891-e80e-4457-8799-a4972c8a1f39" />

  <img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/04fa2e40-ab8d-4ef6-a225-d8e4aff2320d" />

  We will see all the model paramteres required for the process.</br>
  <img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/e033edfd-3304-474f-925f-99a36bf72883" />

  <img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/baa1c253-f071-4bd2-b701-68fedb5be846" />

  We have different W and L values which pre-described. For simulation we need to take any one value which is present inside the library.</br>

  <img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/8fdfae2f-f937-4500-85fc-9e7c89870478" />

  Now go inside `models` --> `lib.spice` file. We will see library files which are present for nfet and pfet. The corner files are present, include Typical, slow-fast and fast-fast corner files.</br>

  <img width="1278" height="800" alt="Image" src="https://github.com/user-attachments/assets/66d2db60-2c01-4568-b74a-6e76c04746a6" />
  <img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/f83d57a4-ced9-49d8-a8a1-cd396cdefb7d" />

Inside `design` --> open day1 file.</br>

<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/54f150ee-51a2-43e2-b886-90df69c3b1f7" />
<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/aa079656-1a7e-4705-ba16-f1010ca81d92" />
Above we see Vdd varying from 0 to 1.8 volts with step size of 0.1V and Vgs sweeping from 0 to 1.8V and with step size of 0.2V

Let us do the spice simulations:
<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/4ac80b7c-6455-4600-9085-a76ba66fe8bc" />

<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/820c2138-e28f-4c1a-a3a1-d54669e4576a" />

<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/6142f189-20cb-4bba-8918-ed8b1ec64f83" />

We will get the plot of Id vs Vds at different Vgs values.</br>

<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/b25a11cc-6124-4546-8e80-363d0df0f692" />

To check the value of Id for corresponding Vds and Vgs, just left click and see.</br>

<img width="310" height="172" alt="Image" src="https://github.com/user-attachments/assets/e2e19848-8536-4215-83f6-664aa9ab0bd4" />

### L5 SPICE lab with Sky130 models
If we go inside `models` folder, we will see `all.spice` file. If we open it we will see the scale of Width and Length.</br>
<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/0f6dfb1f-7668-466a-8ba7-c9ac5beacb77" />

We can see that W and L values are in microns.</br>

# NgspiceSky130-Day2-Velocity saturation and basics of CMOS inverter VTC

## SPICE simulation for lower nodes and velocity saturation effect

### L1 SPICE simulation for lower nodes
We have seen the curve for Id vs Vds, for different values of Vgs.</br>

<img width="1297" height="658" alt="image" src="https://github.com/user-attachments/assets/c10158ab-7588-4862-96a0-19125d4a3e25" />

In the above graph the area left of curve; Vds=Vgs-Vt is Linear region as current is increasing linearly, the area right is Saturation region with slight increase in current due to velocity saturation and below is the Cut off region.Also this case is when the channel length is large.</br>

Now we are taking different W and L, but the ration of W/L is same as previous, so the Id should not change. But this is not the case practically.</br>
Below is the spice deck, where only the values of W and L is changed, rest everything remains same.</br>

<img width="872" height="442" alt="image" src="https://github.com/user-attachments/assets/09eec98c-92a0-409e-a6c5-5b2a18e8289d" />

### L2 Drain current vs gate voltage for long and short channel device
Let us compare the two simulations we did.

<img width="1385" height="547" alt="image" src="https://github.com/user-attachments/assets/0dd21cb8-3868-4074-909f-accde3fa2556" />

**There are some Observations:**
* **Observation 1**- If we see Id values for different Vgs and for Vds=2.5V, there is a quadratic dependency of Id on Vgs. Whereas for short channel device, at Vds=2.5V, the current is increasing linearly due to velocity saturation.</br>

<img width="1385" height="547" alt="image" src="https://github.com/user-attachments/assets/3eb690d9-a38c-4c97-a9b2-2b0b5148ff63" />
<img width="747" height="540" alt="image" src="https://github.com/user-attachments/assets/7f388d3d-9e7c-45ad-b70b-65a1d846f961" />

Now we will plot graph of Id vs Vgs and sweeping Vds or keeping Vds constant = 2.5V.</br>

<img width="855" height="442" alt="image" src="https://github.com/user-attachments/assets/658d2ba4-4e01-4e20-9a01-e949f3f88cb9" />

The syntax explains that what will be there on left hand side will be sweeped at every value on right hand side. For example here for every value of Vdd, Vin will be sweeped. The plot we get is quadratic, it is only when Vds=2.5V </br>

<img width="776" height="641" alt="image" src="https://github.com/user-attachments/assets/fd8321e8-6235-4c84-aa42-411747b0f599" />

Let us see the same effect for short channel device. For L=0.25 micron.
<img width="1332" height="592" alt="image" src="https://github.com/user-attachments/assets/ffba63a2-5ce1-42c5-a7f0-0f61fe194d12" />

### L3 Velocity saturation at lower and higher electric fields
For short channel we will see more of a linear behaviour as the Vgs increases. This is due to velocity saturation effect.</br>

<img width="1332" height="592" alt="image" src="https://github.com/user-attachments/assets/95aa490e-3dc0-4875-b74a-836c1ae07486" />
So, for lower node we will have 4 regions of operations: **Cut Off, Linear, Saturation and Velocity Saturation**

**Velocity Saturation**
We know velocity and electric field are related to each other with equation `v=uE`, where v is velocity, E is electric field and u is mobility. Velocity increases linearly with electric field over certain electric field value after which it gets saturated. This is due to scattering at higher fields and mobility decreases. </br>

<img width="973" height="506" alt="image" src="https://github.com/user-attachments/assets/57f60dd0-b579-4e67-962d-03c21c430e49" />

Velocity saturation happens for higher gate-source voltages.</br>

<img width="1011" height="470" alt="image" src="https://github.com/user-attachments/assets/bf8911ed-1708-4c95-adc1-f6816f66a689" />

### L4 Velocity saturation drain current model
<img width="987" height="473" alt="image" src="https://github.com/user-attachments/assets/cbe1cdbb-8b18-4c19-97c6-be3e4244fb34" />

Let us take Vgs-Vt=Vgt because we will be taking Vgs as large values. Current equation we will be using as shown above, For lower values of Vds we will neglect the 'lambda' term.</br>
There is one more technology paramter which is "Vdsat", it is the velocity of gate when the device just enters the Velocity saturation region.</br>
<img width="831" height="212" alt="image" src="https://github.com/user-attachments/assets/2e70d7d1-4891-4488-90e8-93f9b5f1322c" />

<img width="1026" height="536" alt="image" src="https://github.com/user-attachments/assets/724c8f7e-e772-4006-9f39-05d7a8e06b56" />

<img width="1080" height="540" alt="image" src="https://github.com/user-attachments/assets/13ace523-0233-4dd0-802d-d1ab5f026de6" />

<img width="1006" height="538" alt="image" src="https://github.com/user-attachments/assets/2d5432ec-2438-41c5-9b52-2f658a17c006" />

<img width="1331" height="583" alt="image" src="https://github.com/user-attachments/assets/5a5755f0-0723-4aea-8f07-e277cf3fdf18" />

In the above equation, it seems when W is constant and L is lowered then Id should increase, But it is not so practically.</br>

* **Observation 2** - The saturation current for lower nodes is low instead of being high. This is because Velocity saturation tends to saturate the device early so the peak current we see for lower nodes is much lesser than for higher nodes.</vr>
<img width="1370" height="576" alt="image" src="https://github.com/user-attachments/assets/82010154-16a3-4079-a57c-e5a7435b9507" />

### L5 Labs Sky130 Id-Vgs
We will now do simulation for lower nodes. Inside day2 design file.</br>

<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/7ff99d62-f2aa-4051-ab89-fdd6957b1bbd" />

<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/186defaf-4efd-4fb7-8bc0-eae28cea8738" />

We can see above, simulation is being done for L=0.15u and W=0.39u.</br>
<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/0112c1fb-efa5-4eb2-a5c2-9c34923067ab" />
<img width="1280" height="800" alt="Image" src="https://github.com/user-attachments/assets/86324146-c031-450c-8549-291730b1524e" />

<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/494be3fa-221f-44ba-80ca-ff0c7b6edfc3" />

The above plot is Id vs Vds for different values of Vgs. We can see for lower values of Vgs it is showing quadratic behaviour and for higher values of Vgs it is showing Linear behaviour. Now if want to see the peak current for Vgs=1.8V, just 'press' left click on mouse at Vgs=1.8V.</br>

<img width="310" height="106" alt="Image" src="https://github.com/user-attachments/assets/4addcabd-97f3-4906-b17b-328877b0bb21" />
So we can see it is approximately 198uA.</br>

**Now let us observe Id vs Vgs**
<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/af6e3b55-d182-45ab-b1cb-d2a8d7ceb647" />

Here again we are taking values for L=0.15u and W=0.39u, Keeping Vds constant at 1.8V and sweeping Vgs from 0 to 1.8V with step of 0.1V.</br>

<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/6a735afb-9cec-4b59-ab26-a68afcd52226" />
<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/1e62fa1a-870c-4dae-9738-fbd9e613a46d" />

<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/ef3102ea-ba16-4ac9-843e-ac73332af8a7" />
In the above graph we can see that, due to short channel effect we are seeing a linear behaviour for higher Vgs and Vds being constant.</br>

### L6 Labs Sky130 Vt
Now we will calculate Threshold Voltage Vt for Id vs Vgs curve.

<img width="1280" height="800" alt="Image" src="https://github.com/user-attachments/assets/8d49d3d1-79d1-4c92-b0ec-87849de28214" />

In the curve we can see that Vt is the value when current increases drastically for small change in Vgs. To calculate we will draw tangent on the curve and see where it touches.</br>

<img width="302" height="51" alt="Image" src="https://github.com/user-attachments/assets/ca01512a-715b-4772-ad59-aacec7c17174" />

It comes at around 0.75V.

## CMOS voltage transfer characteristics (VTC)

### L1 MOSFET as a switch
We will now look at the device parameters from the switch point of view.</br>

<img width="907" height="508" alt="image" src="https://github.com/user-attachments/assets/6bb70912-c36e-4031-bf01-7e05871b28a8" />
The above shows MOSFET as a switch:
* When |Vgs|<Vt, device is OFF and it acts as open switch
* When |Vgs|>Vt, device is ON and it acts as closed switch

<img width="1220" height="685" alt="image" src="https://github.com/user-attachments/assets/48869cbb-daee-4a3b-96a8-bdd0fb45a79f" />

### L2 Introduction to standard MOS voltage current parameters
We are trying to get the equivalent circuit of CMOS when Vin is 'high' and 'low', so that we can get the Voltage Transfer Characteristics (VTC) and therefore calculate the delay of the cell.</br>

* When we take Vin as 'high' and equal to Vdd, PMOS will be OFF and NMOS will be ON
<img width="1292" height="680" alt="image" src="https://github.com/user-attachments/assets/f65a1301-44f9-482e-b8dd-7b5cb3d39e47" />

* When we take Vin as 'low' or equal to '0', PMOS will be ON and NMOS will be OFF.
<img width="1347" height="696" alt="image" src="https://github.com/user-attachments/assets/c15bdbc8-99af-48e0-a23c-726e7e415b66" />

So we can see that when Vin=Vdd there is a direct path that exists between Vss and Vout, the capacitor CL discharges through the resistor.</br>
Similarly when Vin=0 there is a direct path between Vdd and Vout, CL charges.</br>
<img width="1322" height="428" alt="image" src="https://github.com/user-attachments/assets/a4f22e15-1c9a-44cf-bfa2-e27b37557439" />

Let us give the naming convention of the CMOS 

<img width="506" height="618" alt="image" src="https://github.com/user-attachments/assets/7225993f-5a53-4456-9959-3cdf52d77960" />

ALso the current in both the condition is Idsn(drain to source for NMOS) and Idsp(Drain to source for PMOS)
And **Idsp = -Idsn**, both are opposite in direction to each other.

### L3 PMOS/NMOS drain current vs drain voltage
<img width="485" height="677" alt="image" src="https://github.com/user-attachments/assets/f2026254-f2b7-4623-967a-79fbc649a8ea" />

Now if we talk about the curve between Idsn Vs Vdsn and Idsp Vs Vdsp, it is as shown below.

<img width="897" height="432" alt="image" src="https://github.com/user-attachments/assets/2e55422f-9659-4ce7-b6ac-b1fe6d41d1a0" />

### L4 Step1- Convert PMOS gate-source-voltage to Vin
We have seen various internal voltages, but actually in terms of user's perspective we can't see the internal voltages and only see the external Vin and Vout. From these we calculate the VTC and eventually we get to know the delay.</br>

**Now we will see the steps to obtain Voltage Transfer Characteristics(VTC) for static CMOS inverter:**
*Assumption: Let us assume that it is a long channel device with Vdd=2V*
* We will fix the Vgs values as shown below
  <img width="372" height="237" alt="image" src="https://github.com/user-attachments/assets/081d616c-e17f-4741-8a96-0d5eae2b2b9a" />
  
* We know that Vgsp= Vin-Vdd, So we get the above values.So we get Vin = Vgsp+Vdd, we are trying to convert all the voltages as function of Vin and Vout.
* We will try to plot the graph of PMOS in terms of Idsn, the plot will be as shown below. We can see that the corresponding Vin value of Vgsp is being plotted as shown in the above table.

  <img width="871" height="443" alt="image" src="https://github.com/user-attachments/assets/cd415d3f-042b-460e-8314-4bb28d50d663" />

### L5 Step2 & Step3- Convert PMOS and NMOS drain-source-voltage to Vout
Now we be converting the Vdsp and function of output voltage Vin. We know **Vdsp = Vout-Vdd**.</br>
Let us convert Vdsp into Vout. So to get Vout there is a shift of Vdd towards left hand side.</br>

<img width="1333" height="391" alt="image" src="https://github.com/user-attachments/assets/c9709e57-c876-4521-9ff6-88fb68f9927c" />

We can see that whenever Vout=2V that means Vdsp=0V and Vdd=2V (given), then The current is zero and capacitor at the output is discharged. This is true only when PMOS is in combination with NMOS and forms a CMOS inverter.</br>
Let us take another example, when Vout=0V, that means -Vdsp=2V and Vdd=2V, so at every gate voltage of Vin we will see a finite current whenever Vout=0V. As Vout=0V, the capacitor is completely discharged and we need to charge that, so that is the charging current required. So, here we get the load curve for PMOS</br>

<img width="513" height="392" alt="image" src="https://github.com/user-attachments/assets/3a31512c-bd15-4f84-8a43-cb125285ad24" />

Now we will try to get the "load curve" for NMOS transistor from this equations.</br>
<img width="223" height="75" alt="image" src="https://github.com/user-attachments/assets/ede06e12-72e7-4da9-8341-820177ed7b4e" />

It is actually simple as Vgsn = Vin and Vdsn = Vout, directly we can get the graphs.</br>

<img width="410" height="287" alt="image" src="https://github.com/user-attachments/assets/e434b1a5-c734-43c2-9565-19714e01f38e" />
<img width="892" height="380" alt="image" src="https://github.com/user-attachments/assets/143a185e-09e5-4c51-8964-eae5b983c47c" />

### L6 Step4- Merge PMOS-NMOS load curves and plot VTC
We will now merge the above two curves and obtain the voltage transfer characteristics(VTC) for CMOS inverter.

<img width="1340" height="412" alt="image" src="https://github.com/user-attachments/assets/e06060aa-bb37-4abc-a225-7cce4569c224" />
For this we will superimpose both the Load Curves to get the VTC. We are doing this to find out the common point between Vin and Vout of both NMOS and PMOS.</br>

<img width="573" height="361" alt="image" src="https://github.com/user-attachments/assets/60499256-909d-4fad-ba5b-5a5e58d4939d" />

So the  range of Vin and Vout is 0V-2V.</br>

* When Vin = 0V, Vout = 2V; NMOS is Cut Off and PMOS is in Linear region
* When Vin = 0.5V, 1.5V<Vout<2V; NMOS is in Saturation region and PMOS is in Linear region.
* When Vin = 1V, 0.5V<Vout<1.5V; NMOS and PMOS are in Saturation region.
* When Vin = 1.5V, 0<Vout<0.5V; NMOS is Linear region and PMOS is in Saturation region.
* When Vin = 2V, Vout = 0V; NMOS is in linear region and PMOS is Cut Off

<img width="1332" height="687" alt="image" src="https://github.com/user-attachments/assets/e484815f-7533-4c87-a6c3-ca79158ac59e" />

# NgspiceSky130-Day3-CMOS switching threshold and dynamic simulations

## Voltage transfer characteristics-SPICE simulations

### L1 SPICE deck creation for CMOS inverter
We will now simulate the VTC. For that we need to **create the SPICE deck**. It is a connectivity information (Netlist). As there is information about substrate, the circuit is as shown below.Here M1 is PMOS and M2 is NMOS</br>

<img width="546" height="501" alt="image" src="https://github.com/user-attachments/assets/87648d3d-9f23-4e6a-b66a-872306e570f1" />

Next we will write down the **Component Vlaues**, keeping W/L for both NMOS and PMOS same.</br>

<img width="622" height="487" alt="image" src="https://github.com/user-attachments/assets/01bb49d8-39b6-40e1-850f-6a6a95dc5946" />

Next we will assume the **Vin and Vout values**

<img width="585" height="482" alt="image" src="https://github.com/user-attachments/assets/38af526d-c53a-4ff7-91c5-bd804fd572da" />

Next step is to **Identify the Nodes** (Node is the point where two components meet)

<img width="766" height="532" alt="image" src="https://github.com/user-attachments/assets/e7a2d759-0ff9-4c2c-939e-ac4af8840cae" />

**Name the nodes** In model file we will mention like, 2.5V input lies between Vin and 0, similarly Vdd lies between vdd and 0.

<img width="592" height="482" alt="image" src="https://github.com/user-attachments/assets/683acee0-3468-498a-9f94-c804122c5a4b" />

Now let us write the SPICE deck:

<img width="1227" height="585" alt="image" src="https://github.com/user-attachments/assets/1b54b47c-edea-4a16-ac0d-fe40405cd393" />
We know for Mosfet the syntax is DGSS(Drain gate source and substrate).

### L2 SPICE simulation for CMOS inverter
<img width="1197" height="582" alt="image" src="https://github.com/user-attachments/assets/6d58c77a-50fe-4eab-9891-287d7a98ae44" />
<img width="1192" height="553" alt="image" src="https://github.com/user-attachments/assets/a06f6d8e-c074-4aa9-9946-6056ed71f927" />
<img width="1280" height="592" alt="image" src="https://github.com/user-attachments/assets/f4e7acd7-6158-432b-8003-b2c74656f9b0" />

Next comes the **Simulation Commands**</br>
Here we will be sweeping the gate input voltage from 0 to 2.5V with steps of 0.05. We need to find the VTC, for this only we will be sweeping the input voltage and measuring the output voltage.</br>
Final step is to describe the **Model files**, all the information about the technological parameteres is given inside the model files.</br>

<img width="1223" height="565" alt="image" src="https://github.com/user-attachments/assets/1bd6f151-618b-4612-82fd-6b43f7eec459" />

Now we will do the SPICE simulation for Wn=Wp=0.375u, Ln=Lp=0.25u, Wn/ln=Wp/Lp=1.5. Below is the VTC we get for the above netlist.</br>

<img width="743" height="567" alt="image" src="https://github.com/user-attachments/assets/91c4ab55-57f1-45ab-826b-b9a9631647ee" />

Next we will get the VTC for Wn= 0.375u, Wp= 0.9375u, Ln,p=0.25u; Wn/Ln=1.5, Wp/Lp=2.5  (PMOS width is 2.5 times more than NMOS)

<img width="741" height="572" alt="image" src="https://github.com/user-attachments/assets/5d83f191-3962-4e25-99b3-aa5d3f520d92" />

If we observe the previous graph is left shifted slightly. This happens because NMOS is more stronger than PMOS in previous graph.</br>

### L3 Labs Sky130 SPICE simulation for CMOS
We now get the VTC characteristics

<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/854eb3e3-126c-4e96-a2f9-ec01fd75b493" />
We are using both pfet and nfet for CMOS inverter. We can see that W/L ratio of pmos is 2.33 times greater than that of nmos. And we will be sweeping Vin from 0 to 1.8V with step isze of 0.01V and plotting the Vout.</br>

<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/549b1602-d49e-4ddc-9709-b723fcb4082f" />
To get the plot type `ngspice` and `plot out vs in`.

<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/bd479186-417c-4264-af7d-5345a350a596" />

<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/f3e872a0-5cb7-43ac-97cf-e074b8878e24" />

Now we need to know the Switching Threshold from this graph, it is the point when Vin=Vout.</br>
To zoom in the curve; press righ mouse button + hold it.</br>

<img width="1280" height="800" alt="Image" src="https://github.com/user-attachments/assets/304f8c7b-14d1-493e-95ed-d48792e73eec" />
So switching threshold for W/L=2.3 is around 0.876V</br>

<img width="302" height="51" alt="Image" src="https://github.com/user-attachments/assets/8d4d61fb-efb4-4b27-b018-f1d906e4555d" />

We will now see the transient analysis:</br>
For that we will go inside the tansient SPICE file for day3</br>

<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/d547618f-c9fe-4132-901c-9034677e40a0" />
We can see that it is for typical corner as before and the W/L is also same. But now we taking transient pulse from 0v to 1V with shift of 0 with rise time and fall time being 0.1ns and 0.1ns respectively, pulse width of 2ns and total time period of 4ns. Let us run this.</br>

<img width="1280" height="800" alt="Image" src="https://github.com/user-attachments/assets/f6abf1a6-7ea5-4c65-bf0a-200b20d33dbb" />
<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/0ef0308d-958f-43c1-a506-fff24ae68d58" />

So for rise delay and fall delay, we need to consider 50% of output curve i.e. at 0.9V; out-in.</br>
<img width="305" height="69" alt="Image" src="https://github.com/user-attachments/assets/c45275cf-be29-4074-ad9d-9c36cf09d616" />

Therefore **Rise delay = 2.484ns-2.171ns = 0.313ns**

For fall delay, consider while falling.</br>

<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/4c675f5c-cef5-4f78-8692-67398bbf94eb" />
<img width="305" height="69" alt="Image" src="https://github.com/user-attachments/assets/3b0b71fa-f6ce-4a08-b5f3-1d4e3c8d65b1" />

Therefore **Fall Delay = 4.333ns-4.050ns = 0.284ns**

## Static behaviour evaluation-CMOS inverter robustness-Switching Threshold

### L1 Switching Threshold, Vm
Let us compare the two different CMOS inverters with different W/L ratios of PMOS and NMOS, we can see that the shape of the VTC is same in both the cases only the switching threshold is different. This shows the robustnesss of CMOS inverter.</br>

<img width="1243" height="578" alt="image" src="https://github.com/user-attachments/assets/c246dc3c-6686-4d8f-b8a5-74136a9323de" />
Let us find out the Switching threshold, Vm in both the cases by drawing a 45 degree line.</br>

So, in first case Vm comes out to be somewhere around 0.9V and in second case Vm=1.2V.</br>
<img width="1168" height="417" alt="image" src="https://github.com/user-attachments/assets/7b300b9a-c5ee-4a11-ab44-6bc6027f8b63" />

This is the area where PMOS and NMOS both are in saturation region. Current flows from both the transistor, it is actually a dangerous situation.

<img width="1083" height="462" alt="image" src="https://github.com/user-attachments/assets/5b52f85c-c43e-4b4f-b38f-e51e8fe28170" />

### L2 Analytical expression of Vm as a function of (W/L)n and (W/L)p
We will now calculate the value of Vm w.r.t the NMOS and PMOS width and length. </br>
<img width="553" height="367" alt="image" src="https://github.com/user-attachments/assets/6c11d77c-26a3-46e5-bf6c-349740e6eb00" />
<img width="860" height="53" alt="image" src="https://github.com/user-attachments/assets/b8533cc5-176d-4cb7-97c3-7d6ad5f4ec88" />
<img width="557" height="148" alt="image" src="https://github.com/user-attachments/assets/aacac08b-2543-4f88-8ddb-ce58cad2b763" />

### L3 Analytical expression of (W/L)n and (W/L)p as a function of Vm
Now here we will calculate the value of W/L for PMOS and NMOS when Vm is given.</br>
We have to move in reverse fashion, as we need to calculate W/L ratio of PMOS and NMOS such that Switching threshold is exatly half of the power supply Vdd = 2.5V, therefore required Vm = 1.25V.</br>
We will start from the current equation itself i.e. **Idsn = -Idsp**

<img width="962" height="362" alt="image" src="https://github.com/user-attachments/assets/4abd767b-176b-42c2-9e2e-bdf52323fed2" />
Expanding Kp and Kn (Gain factor) </br>
<img width="517" height="92" alt="image" src="https://github.com/user-attachments/assets/950f6372-d1d7-4c18-8cfd-5b1f35cdfce5" />
<img width="517" height="92" alt="image" src="https://github.com/user-attachments/assets/a532b030-2296-4ff8-981d-2ab29cd88dea" />

Now here on the RHS all are constants and we will get the values from the model files except Vm, If we know Vm then we can get the W/L ratios.</br>
So now this will allow us to find out for what value of W/L ratio of PMOS will be greater than NMOS based on values of Vm.</br>
We will now see the behaviour of CMOS for below difference in W/L ratios of PMOS and NMOS.</br>

<img width="301" height="233" alt="image" src="https://github.com/user-attachments/assets/8534791b-2793-4986-bdad-4a2ef6bde1fe" />

### L4 Static and Dynamic simulation of CMOS inverter
* For (W/L)n = (W/L)p = 1.5</br>
  <img width="750" height="567" alt="image" src="https://github.com/user-attachments/assets/1c8f3e81-2023-429d-9a9e-b80e35d3ad09" />

  We can also calculate the "Rise Delay" and "Fall Delay" by using the transient analysis, just like we did earlier.</br>
  <img width="1256" height="512" alt="image" src="https://github.com/user-attachments/assets/836bb013-63a3-44aa-b0d5-d640359c35f7" />

### L5 Static and Dynamic simulation of CMOS inverter with increased PMOS width
We will be doing the SPICE simulations for increased width of PMOS transistors and compare the results.</br>
* (W/L)p = 2(W/L)n</br>
  <img width="1181" height="507" alt="image" src="https://github.com/user-attachments/assets/7333b09a-2e41-40b2-881e-373214b16c5b" />

We can see that the Vm is now increased as the PMOS has become more stronger and it needs more current to charge the output load capacitor.</br>
* (W/L)p = 3(W/L)n</br>
  <img width="1197" height="507" alt="image" src="https://github.com/user-attachments/assets/f3bea4a2-8853-4330-8886-86e6ab224069" />

<img width="1241" height="512" alt="image" src="https://github.com/user-attachments/assets/abf77cdf-93df-45b2-8373-b9d526a1c8e6" />
<img width="1207" height="512" alt="image" src="https://github.com/user-attachments/assets/978a4960-3442-4ba5-bd1b-e8f336f8812a" />

*Note: Rise delay decreases with increase in PMOS width, this shows the time required to charge the output capacitor decreases significantly this is because we have a bigger area.* </br>

### L6 Applications of CMOS inverter in clock network and STA
The final data set we got from above experiment is shown below:

<img width="692" height="236" alt="image" src="https://github.com/user-attachments/assets/0359ac26-996d-423d-bd27-99e08b6dddaa" />

There are some conclusions we draw from this experiment: </br>
* During fabrication, there can be slight variation in sizes of PMOS and NMOS from the required one, but the robustness of CMOS inverter is such that, there is not much difference in the Vm with change in sizes.
* When (W/L)p = 2(W/L)n, we see that RISE-FALL delay are approximately equal, if we simulate then we can get the ratio factor such that the Rise delay and fall delay are equal to each other. This shows "Symmetry" of CMOS inverter.
  
  *This is a typical characteristic of Clock Inverter/buffer where we want the rise delay and fall delay to be equal.* </br>
  <img width="1110" height="653" alt="image" src="https://github.com/user-attachments/assets/30d33241-5e2f-4389-9a80-cd8d2ad5baaf" />
* Other types of cells can be used according to the data path requirement

# NgspiceSky130-Day4-CMOS Noise Margin robustness evaluation

## Static behaviour evaluation-CMOS inverter robustness-Noise Margin

### L1 Introduction to Noise Margin
Now we will learn CMOS inverter's robustness towards the Noise Margin. Also we see the Noise margin evaluation for CMOS inverter. </br>
**Noise Margin**: It is a measure of how much unwanted electrical noise a logic circuit can tolerate on its input without producing an incorrect output. </br>

For example if we consider an ideal Inverter, for inputs 0/1 it gives output as 1/0. The slope of switch is infinite. </br>

<img width="557" height="451" alt="image" src="https://github.com/user-attachments/assets/2465a4e2-199d-4698-aa7d-58f0b42f0c6f" />

But practically the slope won't be infinite, due to presence of resistances and capacitances there will be delay. Therefore we will get a finite slope </br>

<img width="368" height="316" alt="image" src="https://github.com/user-attachments/assets/f8f2f3f3-dc21-45eb-90b7-c9f2fdb8ef94" />

We will now see that whenever the input is between 0 to VIL(input low voltage); the output will be VOH(output high). </br>
And whenever the input is between VIH(input high voltage) and Vdd; output will be VOL(output low voltage). </br>
<img width="405" height="342" alt="image" src="https://github.com/user-attachments/assets/8e3c22bf-b012-4a75-a08d-910511ed2980" />

### L2 Noise Margin voltage paramters
Considering the more practical scenarios and non idealities of an inverter, the curve we get is as shown below. So here the when the 0<Vin<VIL --> output is VOH<Vout<Vdd ; and when the input is VOL<Vin<Vdd --> output is 0<Vout<VOL. Also **VOL<VOH<Vdd** as VOH will be output high for the next inverter which will be connected and **0<VOL<VIL** as it will be the output low for the next inverter. </br>

Also, the slope is approximately -1, as for increase in input, output is reducing. </br>

<img width="356" height="337" alt="image" src="https://github.com/user-attachments/assets/d848d4c0-de9b-4b6b-8c6a-f3006bae557c" />

### L3 Noise margin equation and summary
Now we will calculate the noise margin equation, for that we will plot the voltages on the same scale.</br>

<img width="733" height="443" alt="image" src="https://github.com/user-attachments/assets/c25a3266-d8f3-4e16-8afa-298756b3a59d" />
In the above scale: </br>
* **Noise amrgin High NH** - value between VIH and VOH. </br>
* **Noise Margin Low NL** - value between VIL and VOL. </br>

So, any value which lies in between noise margins is considered either 1/0 and considered to be tolerable. Apart from this region the value is "Undefined" and the logic level can swing between 'high' and 'low'.

<img width="783" height="423" alt="image" src="https://github.com/user-attachments/assets/80791538-0e36-46a8-9bf1-043e740dd778" />

<img width="822" height="481" alt="image" src="https://github.com/user-attachments/assets/6443e129-644a-4d0d-a4c4-0439ba4165de" />

### L4 Noise margin variation with respect to PMOS width
We will evaluate the noise margin depending upon the PMOS width and ultimately prove that how CMOS inverter is robust to the noise margins.</br>
First, we will find the points where the slope = -1 and extend the lines towards x-y axis.</br>

<img width="1207" height="542" alt="image" src="https://github.com/user-attachments/assets/5ab8cb26-4ab7-4e77-9a04-be82cfcdac12" />
The larger the Noise margin, stronger is CMOS inverter and immune to Noises.</br>

<img width="1175" height="523" alt="image" src="https://github.com/user-attachments/assets/98daed0b-5528-4d72-8a99-06806511d1b8" />
<img width="1197" height="503" alt="image" src="https://github.com/user-attachments/assets/89b5f850-df64-4e6e-abcb-366cc3755d13" />
<img width="1203" height="517" alt="image" src="https://github.com/user-attachments/assets/13199ec4-704c-4812-aba2-38257330e40b" />

For (W/L)p=4(W/L)p and (W/L)p=5(W/L)p noise margins are same, so even if we increase the widths further noise margin will be static. 

<img width="677" height="226" alt="image" src="https://github.com/user-attachments/assets/fca7bcac-471c-4114-8c64-4b97cba1f5b0" />

Here also we can verify the robustness of CMOS inverter. </br>

Also we come to know the ranges for "Digital design" and "Analog design" in the CMOS inverter.</br>

<img width="741" height="546" alt="image" src="https://github.com/user-attachments/assets/3e9a0cf6-a232-4ff2-ad4c-214b03803af3" />
<img width="772" height="542" alt="image" src="https://github.com/user-attachments/assets/56c5c94d-b59f-456c-ba92-b22fab03b6d9" />

### L5 Sky130 Noise margin labs
We will now plot Noise margins

<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/a9736caa-8508-4460-b281-95c5e3f8e884" />
<img width="786" height="533" alt="Image" src="https://github.com/user-attachments/assets/8d4db63b-bbef-4b68-9301-9bf916ce86d8" />

We are taking the W/L ratios of PMOS to NMOS as 2.77 and sweeping the Vin from 0 to 1.8V with stepsize of 0.01V.

<img width="1280" height="800" alt="Image" src="https://github.com/user-attachments/assets/3c254b16-7d8d-45e5-801a-c69f4be94012" />
<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/1243c8fc-a832-46d4-9017-c339f3208307" />
<img width="305" height="69" alt="Image" src="https://github.com/user-attachments/assets/baa075bc-2aa3-444a-9078-3beeedd33593" />

We will take the point where the slope is -1 ; x axis will give VIL and VIH, whereas y axis will give VOH and VOL.

**Noise margin NH = VOH - VIH = 1.69275-0.98 = 0.71275** </br>
**Noise margin NL = VIL - VOL = 0.78181-0.10724 = 0.67457** </br>

# NgspiceSky130-Day5-CMOS power supply and device variation robustness evaluation

## Static behaviour evaluation-CMOS inverter robustness-Power supply variation

### L1 Smart SPICE simulations for power supply variations
While evaluating the robustness of CMOS inverter another factor is **Power Supply Scaling**. On reducing the gate length, the operating power is also reduced. On power scaling the Cmos characteristics should not change.</br>

We will check by simulation, taking two cases.

<img width="1172" height="328" alt="image" src="https://github.com/user-attachments/assets/03dcd0b9-4dd3-4762-83b2-9cbb882e7bc3" />
<img width="723" height="442" alt="image" src="https://github.com/user-attachments/assets/e403056b-c4bb-4b18-a67c-baf5b02842ab" />
<img width="717" height="436" alt="image" src="https://github.com/user-attachments/assets/f357c6d2-fa02-43bc-bf51-184494cf8858" />
<img width="421" height="171" alt="image" src="https://github.com/user-attachments/assets/25f4e021-6818-4e30-85d9-cf300b35bd03" />

We will now plot the VTC charactersitics for Vdd= 2.5V, 2V, 1.5V, 1V, 0.5V;

<img width="742" height="568" alt="image" src="https://github.com/user-attachments/assets/87cf496c-6386-4374-9e92-1a6ef71959c1" />

### L2 Advantages and disadvantages using low supply voltage
We will now analyse the curves we got in after the simulation and see what are the advantages and disadvantages using low supply voltage.</br>
The first factor is to check the "Gain" for all the supply voltages. "Gain Factor" is change in the output voltage divided by change in the input voltage.

<img width="968" height="516" alt="image" src="https://github.com/user-attachments/assets/dd11da87-d570-4fe1-9439-bd449e39af6a" />

<img width="976" height="547" alt="image" src="https://github.com/user-attachments/assets/102b9c1b-82ce-4d72-bc7e-fb502591c636" />

There is energy lowering for low supply voltage.

<img width="1000" height="526" alt="image" src="https://github.com/user-attachments/assets/f9a05a5f-40c0-4bad-be1f-3cd16f1445f4" />
<img width="927" height="527" alt="image" src="https://github.com/user-attachments/assets/b96be82f-5993-4fd1-9cc2-c0756dc212df" />

* Advantages of low supply voltage
  
<img width="722" height="212" alt="image" src="https://github.com/user-attachments/assets/ab3ef568-d3f7-44cb-a6c5-6524ba5b72ec" />

* Disadvantages of low supply voltage
  Due to low supply voltage, the charging and discharging of load capacitor becomes very slow, due to this the Both rise delay and fall delay will increase and lead to a performance impact.

### L3 Sky130 Supply variation Labs
We will calculate the supply variation.

<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/eeb505a8-7ce5-4cc8-80ae-511722652ec5" />
<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/3ed38dde-b9bc-4f26-9dd7-28ca388c6221" />

The initial supply voltage is 1.8V and we are reducing it with the step of 0.2V, so there will be 6 iterations.

<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/fa40bee9-5ada-421b-959c-53803b0fa996" />
We will calculte the Gain: </br>

* **Vdd=1.8V** </br>

  <img width="305" height="69" alt="Image" src="https://github.com/user-attachments/assets/f8e8b0a8-3aae-4837-9aa4-78ef9efe8d1a" />

  |Gain| = 7.7422 </br>

* **Vdd=0.8V**

  <img width="305" height="69" alt="Image" src="https://github.com/user-attachments/assets/2549924e-b8b7-43f9-b27c-e3314cc9f17e" />

  |Gain| = 8.7788 </br>

## Static behaviour evaluation-CMOS inverter robustness-Device variation

### L1 Sources of variation - Etching process
We will see the sources of variation of VTC characteristics in a CMOS inverter.</br>
First is **Etching Process** </br>
If we see a single inverter layout, we will see the length of gate, the width(common area between polysilicon and diffusion). Due to etching process there can be a variation in length and width of CMOS.

<img width="1208" height="580" alt="Screenshot 2025-10-03 203231" src="https://github.com/user-attachments/assets/f4496266-b2a9-4e21-bb84-54e6519478e4" />

Now considering the inverter chain, the variation can differ with different inverter.

<img width="1288" height="652" alt="Screenshot 2025-10-03 203314" src="https://github.com/user-attachments/assets/a326d12c-e0b7-4daa-bf13-311ccaa8e476" />
<img width="1121" height="618" alt="Screenshot 2025-10-03 203404" src="https://github.com/user-attachments/assets/8683fe6c-a634-4720-98d4-8ef619ab52b1" />

The variation is more at the edges or sides than at the center.

<img width="1324" height="621" alt="Screenshot 2025-10-03 203542" src="https://github.com/user-attachments/assets/998d8d7c-941f-4643-a768-13896c578018" />

Therefore the variation in L and W can change the drain current of CMOS inverter.

<img width="926" height="483" alt="Screenshot 2025-10-03 203633" src="https://github.com/user-attachments/assets/b1c7130a-de89-4cf1-ab2e-064702878082" />

### L2 Sources of variation - Oxide thickness
Another source of variation is **Oxide Thickness*</br>
Let us consider the cross-sectional view of CMOS inverter. We will see the oxide under polysilicon gate, while fabricating the thickness can vary.</br>

<img width="1318" height="561" alt="Screenshot 2025-10-03 203747" src="https://github.com/user-attachments/assets/25b705ca-1d73-4127-a9bc-a69e2af0c8c2" />
<img width="826" height="377" alt="Screenshot 2025-10-03 203848" src="https://github.com/user-attachments/assets/df455509-4718-4074-9eda-bb314e6462c0" />

There is a difference between ideal thickness and actual thickness.

<img width="1205" height="597" alt="Screenshot 2025-10-03 203924" src="https://github.com/user-attachments/assets/a802cce3-df91-4e80-9b34-d2f931de9f8d" />

We know **Cox=Eox/tox**, therefore change in tox can actually change the drain current.

<img width="1162" height="461" alt="Screenshot 2025-10-03 204044" src="https://github.com/user-attachments/assets/d06ee6da-3467-41cb-8a0e-280b15faae56" />

### L3 Smart SPICE simulation for device variations
Now we will be doing the SPICE simulation for device variations, and prove the robustness of CMOS inverter inspite of different extreme conditions.</br>
We will see the characteristics for Strong PMOS and week NMOS, this means PMOS width is wider and it has least resistance. Also for weak PMOS and strong PMOS, that means the width of NMOS is more than PMOS and it has least resitance.</br>

<img width="1148" height="339" alt="Screenshot 2025-10-03 224857" src="https://github.com/user-attachments/assets/398d01a6-ffc4-4a10-86a8-3907d3214b69" />
<img width="594" height="436" alt="Screenshot 2025-10-03 224935" src="https://github.com/user-attachments/assets/41b1f2f6-c4ba-4c71-a8e6-d1fc8e3b4844" />
<img width="695" height="398" alt="Screenshot 2025-10-03 224949" src="https://github.com/user-attachments/assets/9314e15f-c027-47ba-b34e-f35d886e5aff" />
<img width="726" height="321" alt="Screenshot 2025-10-03 225121" src="https://github.com/user-attachments/assets/280f196e-1bde-417a-9955-7a0f2029ee39" />
<img width="753" height="567" alt="Screenshot 2025-10-03 225153" src="https://github.com/user-attachments/assets/33e8fc0e-5220-4dc4-8da9-4c8dd5406e02" />

### L4 Conclusion
We will draw some conclusions from the characteristics we got.

<img width="994" height="537" alt="Screenshot 2025-10-03 231012" src="https://github.com/user-attachments/assets/aec473f9-00f5-4028-b122-fa2922affcb3" />

* The Switching threshold 'Vm' is shifted right in case of strong PMOS and shifted left in case of Strong NMOS. </br>

<img width="1006" height="541" alt="Screenshot 2025-10-03 231027" src="https://github.com/user-attachments/assets/38851b7b-ec82-4400-93d8-c3c651d51ae9" />

* THere not much variation in NOise Margins in both the extreme cases, that means it behaves as a robust inverter in both the cases.</br>

<img width="519" height="169" alt="Screenshot 2025-10-03 231046" src="https://github.com/user-attachments/assets/edd63a58-b8bb-462e-84e5-b8c977d4a4d2" />

### L5 Sky130 device variations labs
We will now do the SPICE simulations for the device variations</br>

<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/cbf0a475-6b72-4cf4-a674-8868d4e64d97" />
<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/b0ee153b-72ab-430f-b81c-f093686e0861" />

We can see that the width of PMOS is quite large than that of NMOS. SO it is clearly strong PMOS and weak NMOS case. The Vm will be right shifted.</br>

<img width="1280" height="800" alt="Image" src="https://github.com/user-attachments/assets/988b574c-e2c0-4f9c-bd18-ce82c3ffffd2" />
<img width="1210" height="773" alt="Image" src="https://github.com/user-attachments/assets/2965ee6d-6f38-4b31-8661-6eab9238a113" />
