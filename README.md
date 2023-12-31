# Wearable Migraine Therapeutic Device
![Wear](https://github.com/RavinduMPK/Wearable-Migraine-Therapuetic-Device/assets/68577937/13625ac1-39d7-477a-ac76-9cacb49299e5)

## Problem

Migraine is a pressing global health issue that lacks a definitive solution. Research surveys have revealed that one out of every ten individuals worldwide experiences the debilitating effects of migraines. This intricate neurological condition manifests with the following characteristics:

- Intense headache localized to one side of the head.
- Moderate to severe throbbing sensation that worsens with movement.
![image](https://github.com/RavinduMPK/Wearable-Migraine-Therapuetic-Device/assets/68577937/010cc8be-0228-44c1-bfe9-29156a174743)

While no permanent medical cure for migraines currently exists, certain methods can alleviate the pain to some extent. Many migraine sufferers resort to massaging their forehead as an external remedy, while others rely on painkillers as a medical treatment. However, these approaches come with limitations:

- Massaging requires interruption of daily activities and is time-consuming.
- Frequent use of painkillers can lead to side effects such as gastritis, ulcers, kidney or liver damage, and more.
These challenges are particularly problematic for students and busy individuals. Given these circumstances, there exists a critical demand for a viable and effective solution to address the issues posed by migraines.

Migraine affects 1 in 10 people globally, causing intense headaches and disruptions. Conventional treatments like painkillers are either time-consuming or carry side effects. An effective and non-invasive solution is needed.
![image](https://github.com/RavinduMPK/Wearable-Migraine-Therapuetic-Device/assets/68577937/ec6f0d62-a57f-44c3-bb3a-c5e0e978a689)


## Solution

Introducing the Wearable Migraine Therapeutic Device – a user-friendly solution that utilizes nerve stimulation to reduce migraine pain. The device offers on-the-go relief, allowing users to continue their activities without interruption.
![Device view](https://github.com/RavinduMPK/Wearable-Migraine-Therapuetic-Device/assets/68577937/207f102b-adaa-4379-954d-7b16d2594fcd)

### Transcutaneous Electrical Nerve Stimulation (TENS)
Transcutaneous Electrical Nerve Stimulation (TENS) has emerged as a popular non-invasive and self-administered technique for pain relief. This method involves the delivery of a minuscule electrical current through the skin using electrode pads attached to the skin surface. A significant advantage of TENS is its minimal side effects.

The underlying mechanism of TENS is based on the gate control theory of pain. This method effectively reduces the transmission of pain sensation messages to the brain by deactivating relevant sensory fibers. Our approach focuses on alleviating migraine pain by strategically placing electrodes on the forehead. We specifically target the afferent paths of the Supratrochlear and Supraorbital nerves, which belong to the ophthalmic branch of the Trigeminal nerve.

Our method employs high-frequency, low-intensity electrical signals. We begin with low intensity and gradually increase it. This approach is designed to stimulate large diameter, low threshold fibers (A-beta) initially, followed by high threshold fibers (A-delta). This sequential stimulation pattern effectively reduces the transmission of migraine pain sensation messages to the brain, providing relief to patients during migraine episodes.

## Key Features

- **Nerve Stimulation:** Utilizes nerve stimulation to alleviate migraine pain effectively.
- **User-friendly Design:** Lightweight and comfortable for extended wear.
- **Safe and Low Power:** Designed with safety and low power consumption in mind.
- **Gradual Relief:** Provides gradual pain relief during operation.
- **Adjustable:** Equipped with an adjustable band to fit different head sizes.

## Technical Specifications

- **Pulse Frequency:** 100 Hz
- **Pulse Duration:** 500 µs
- **Pulse Width:** 250 µs
- **Step-up Intensity:** 30 µs
- **Max Intensity:** 1 mA
- **Weight:** Approximately 50g

### Electrode Pad
![Electrode_pad](https://github.com/RavinduMPK/Wearable-Migraine-Therapuetic-Device/assets/68577937/18317079-b3f8-4d81-9c0c-746f07103728)
- A-Self-adhesive pad
- B-Insulated area
- C-Hook (To hold the electrode pad with the circuit above tightly)

## Architecture

The device's architecture involves a microcontroller, pulse generator, voltage-to-current converter, and feedback outputs. Components work together to generate and deliver the therapeutic effect.

![image](https://github.com/RavinduMPK/Wearable-Migraine-Therapuetic-Device/assets/68577937/9e701492-1ff2-4aa4-a6c3-50d54da9c80c)

### Inputs
The primary input of the device is facilitated by a push-button switch. For this purpose, we have integrated a 6Pin Two Row Through Hole Mount DPDT Self-Locking Mounting Tact Tactile Power Micro Push Button as our switch.

### Signal Generation Unit
The Signal Generation Unit comprises several sub-modules:

### Micro-controller Unit
This module generates a PWM signal with a varying duty cycle. Our micro-controller programming gradually increases the duty cycle over 16 minutes and then decreases it over the next 4 minutes.

![image](https://github.com/RavinduMPK/Wearable-Migraine-Therapuetic-Device/assets/68577937/ee009980-76cd-40de-8acd-9d984233da9f)


### Digital-Analog Converter
This sub-module converts the PWM signal obtained from the micro-controller into an analog stair-case signal. To achieve this, a second-order filter circuit is employed to accurately filter out harmonics while retaining the DC component of the signal.

![image](https://github.com/RavinduMPK/Wearable-Migraine-Therapuetic-Device/assets/68577937/120e0508-868a-4453-b157-053628f959a6)


### Sampling Signal Generator
A sampling signal, operating at around 100Hz, is required to sample the stair-case signal. To generate this, a 555 timer IC is employed. Given the limitation of the micro-controller in generating such a low-frequency PWM signal, this approach is chosen.

![image](https://github.com/RavinduMPK/Wearable-Migraine-Therapuetic-Device/assets/68577937/74917c1c-7c85-40d4-a204-00e84bbcaea2)


### Sampling Unit
This sub-module samples the stair-case signal. We employ a BJT transistor in switching mode, with calculated resistor values for the base and collector ensuring the transistor operates within the switching region.

![image](https://github.com/RavinduMPK/Wearable-Migraine-Therapuetic-Device/assets/68577937/8a682b72-e209-417c-a826-317e2a13397e)


### Voltage-Current Converter
In the final stage of the circuit, the generated voltage signal must be converted into a current signal. To achieve this, we've designed an Op-Amp circuit functioning as a voltage-current converter, ensuring the output current remains independent of the output load.

![image](https://github.com/RavinduMPK/Wearable-Migraine-Therapuetic-Device/assets/68577937/5b8c6da4-7ed3-43cc-b11a-53fd65986bd9)


### Outputs
The primary output of our device is the generated current, delivered through three electrode terminals. Additionally, feedback outputs have been integrated to enhance user-friendliness:

A red LED indicates the device is in Power ON mode.
A green LED indicates the device is in Operating mode.
A buzzer emits a beep sound at the beginning and end of the Operating mode.
Power Supply Unit
The device is powered by four coin cells, regulated by a 7805 IC to ensure a stable supply voltage.

## PCB Design

To realize our wearable migraine therapeutic device, a carefully designed Printed Circuit Board (PCB) was a crucial component of the implementation. Our PCB hosts an array of connectors, buttons, microcontrollers, and integrated circuits (ICs) that collectively form the foundation of our device's functionality. The design and layout were facilitated using the Altium software suite.

### Schematic and Layout
The PCB design process began with the creation of a comprehensive schematic diagram. This diagram served as the blueprint for how the various components would connect and interact. Subsequently, the PCB layout was meticulously planned to accommodate the physical placement of components, connectors, and traces.
![Schemetic](https://github.com/RavinduMPK/Wearable-Migraine-Therapuetic-Device/assets/68577937/03f96336-e838-46bb-8673-5dc2f36d822f)


### Two-Layer PCB Layout
Given the spatial constraints imposed by the device's compact form factor, a two-layer PCB layout was chosen. This design decision enabled us to optimize component placement and routing within the confined dimensions. The careful arrangement of components was essential to ensure effective functionality while minimizing interference and signal degradation.
![First PCB](https://github.com/RavinduMPK/Wearable-Migraine-Therapuetic-Device/assets/68577937/0f82d7b0-08f4-402a-a15c-c3dd5faf63e2)


### Assembly
Upon finalizing the design and layout, the PCB was manufactured according to the specifications. Components were then manually soldered onto the PCB, adhering to the designated positions as outlined in the design. Attention to detail during assembly was paramount to ensure reliable connections and the overall integrity of the device.

The PCB design process was a critical step in bringing our wearable migraine therapeutic device to life. It encapsulated both the functional requirements and the constraints imposed by the form factor, resulting in an efficient and compact solution.
![image](https://github.com/RavinduMPK/Wearable-Migraine-Therapuetic-Device/assets/68577937/9b3714fd-2de2-45e4-833a-6c31342e9ee2)

#### Note: We designed anoter PCB for this and those files avilable in PCB Design folder.

## Enclosure Design

The design of the enclosure for our wearable migraine therapeutic device was a critical aspect of its overall development. Our enclosure underwent meticulous design and planning to ensure optimal functionality, comfort, and aesthetics. We utilized the SolidWorks design software to bring our vision to life.

### SolidWorks Design Software
For the creation of the enclosure, we leveraged the capabilities of SolidWorks design software. This industry-standard tool enabled us to model and visualize the physical form of the device, making it an essential part of our design process.

### Minimization of Mass
A paramount consideration in the enclosure design was the minimization of mass. By strategically selecting materials and optimizing the enclosure's structure, we aimed to achieve a balance between durability and lightweight design. This emphasis on minimizing mass contributes to the comfort and portability of the device.

### Size Miniaturization
The compact nature of our wearable migraine therapeutic device was a crucial factor in its usability. To this end, we prioritized the miniaturization of the device's size while ensuring that all internal components fit seamlessly within the enclosure. This size optimization enhances the device's wearability and ensures user comfort.

### Multi-Part Enclosure Design
To accommodate the complexity of the device's internal components and maintain a streamlined exterior, we divided the enclosure into three distinct parts. Each part was meticulously designed to seamlessly fit together, providing easy access to internal components while maintaining a cohesive and ergonomic exterior.

![Top lid](https://github.com/RavinduMPK/Wearable-Migraine-Therapuetic-Device/assets/68577937/1126d782-fa0a-4ff9-b482-413e12408cf1)
![Bottom lid](https://github.com/RavinduMPK/Wearable-Migraine-Therapuetic-Device/assets/68577937/4e983ec5-30aa-4fea-ae05-282162885352)
![Battery case cover](https://github.com/RavinduMPK/Wearable-Migraine-Therapuetic-Device/assets/68577937/777109b7-9f36-493e-b4ab-3d49a5572c0f)

The enclosure design process was a fusion of creativity, functionality, and innovation. Through the utilization of SolidWorks and a dedication to minimizing mass and size, we achieved a multi-part enclosure that embodies both form and function.
![Assembled Enclosure](https://github.com/RavinduMPK/Wearable-Migraine-Therapuetic-Device/assets/68577937/9269838c-5fe2-4e5d-a743-024e5bb7e7a4)

## Testing
Ensuring the correct and reliable operation of our circuit was paramount to the success of our wearable migraine therapeutic device. Rigorous testing procedures were conducted within the laboratory environment to validate the functionality and accuracy of the circuit.

### Waveform Observation and Validation
During the testing phase, we meticulously observed the waveforms at each crucial sub-module of the circuit using an oscilloscope. By doing so, we were able to ensure that the circuit generated the required waveforms accurately at every step of its operation. These observations provided critical insights into the circuit's behavior and helped us verify the functionality of each sub-module.

### Final Output Waveform
The culmination of our testing efforts resulted in the observation of the final output waveform. This waveform represents the desired therapeutic signal that our device generates. Through careful validation, we were able to confirm that the device was successfully generating the necessary waveform, paving the way for its effective use in providing migraine relief.

For a more detailed breakdown of the observed waveforms and their interpretations, we have provided comprehensive documentation under the "Testing" folder, which offers insights into the waveforms' characteristics, trends, and implications.

## User Interface

- **On/Off Button:** Easily switch the device on or off.
- **LED Indicator:** Indicates device status (On/Off, battery level).
- **USB Port:** Rechargeable design for convenience.
- **Beep Speaker:** Auditory feedback for operation status.


## Budget and Cost

- **Components:** Approx. Rs. 13,180
- **Total Cost:** Approx. Rs. 15,000

## Contact

For more information about the Wearable Migraine Therapeutic Device, contact us:

- **Email:** ravindumadushan005@gmail.com

## References

- Burch, Rebecca C., et al. “Migraine.” Neurologic Clinics, vol. 37, no. 4, Nov. 2019.
- "Second Order Filter | Second Order Low Pass Filter Design." Basic Electronics Tutorials, 10 Feb. 2018.
