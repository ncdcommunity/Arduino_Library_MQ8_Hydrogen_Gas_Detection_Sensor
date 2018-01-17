
[![ADC121C_MQ8](ADC121C_I2CGAS_MQ8.png)](https://store.ncd.io/product/mq-8-hydrogen-gas-sensor-adc121c-12-bit-adc-i2c-mini-module/)

# ADC121C_MQ8
ADC121C_MQ8 is a hydrogen gas detection Sensor.
This Device is available from www.ncd.io [SKU: ADC121C_MQ8_I2CS]
(https://store.ncd.io/product/mq-8-hydrogen-gas-sensor-adc121c-12-bit-adc-i2c-mini-module/)
This Sample code can be used with Arduino.

Hardware needed to interface ADC121C_MQ8 hydrogen gas detection Sensor with Arduino
1. <a href="https://store.ncd.io/product/i2c-shield-for-arduino-nano/">Arduino Nano</a>
2. <a href="https://store.ncd.io/product/i2c-shield-for-arduino-micro-with-i2c-expansion-port/">Arduino Micro</a>
3. <a href="https://store.ncd.io/product/i2c-shield-for-arduino-uno/">Arduino uno</a>
4. <a href="https://store.ncd.io/product/dual-i2c-shield-for-arduino-due-with-modular-communications-interface/">Arduino Due</a>
5. <a href="https://store.ncd.io/product/mq-8-hydrogen-gas-sensor-adc121c-12-bit-adc-i2c-mini-module/">ADC121C_MQ8 hydrogen gas detection Sensor</a>
6. <a href="https://store.ncd.io/product/i%C2%B2c-cable/">I2C Cable</a>

ADC121C_MQ8:

Sensitive material of MQ-8 gas sensor is SnO2, which with lower conductivity in clean air. When hydrogen gas exists, the sensor’s conductivity gets higher along with the gas concentration rising. Users can convert the change of conductivity to correspond output signal of gas concentration through a simple circuit.
MQ-8 gas sensor has high sensitivity to hydrogen gas, also has anti-interference to other gases. This sensor can detect hydrogen, especially city gas.

Applications:

•They are used in gas leakage detecting equipments in family and industry, are suitable for detecting of Hydrogen (H2), avoid the noise of alcohol and cooking fumes, LPG,CO.

## Arduino
Download and install Arduino Software (IDE) on your machine. Steps to install Arduino are provided at:

https://www.arduino.cc/en/Main/Software

Download (or git pull) the code and double click the file to run the program.
Compile and upload the code on Arduino IDE and see the output on Serial Monitor.

How to Use the ADC121C_MQ8 Arduino Library
The ADC121C_MQ8 has a number of settings, which can be configured based on user requirements.

1.Automatic Conversion mode: When these bits are set to zeros, the automatic conversion mode is disabled. This is the case at power-up.When these bits are set to a non-zero value, the ADC will begin operating in automatic conversion mode.

      mq8.setCycleTime(CYCLE_TIME_32);              // Tconvert x 32, 27 ksps
    
2.Alert Hold:This bit tells the Alert will self clear or not.

   0: Alerts will self-clear when the measured voltage moves within the limits by more than the hysteresis register value.
  
   1: Alerts will not self-clear and are only cleared when a one is written to the alert high flag or the alert low flag in the Alert Status register.

      mq8.setAlertHold(ALERT_HOLD_CLEAR);         // Alerts will self-clear

3.Alert Flag Enable:This bit indicates when an alert condition has occurred. When the Alert Bit Enable is set in the Configuration Register, this bit will be high if either alert flag is set in the Alert Status Register.Otherwise, this bit is a zero.

   0: Disables alert status bit [D15] in the Conversion Result register.
  
   1: Enables alert status bit [D15] in the Conversion Result register.

         mq8.setAlertFlag(ALERT_FLAG_DISABLE);     // Disables alert status bit in the Conversion Result register
       
4.Alert Pin Enable:.

   0: Disables the ALERT output pin. The ALERT output will TRI-STATE when the pin is disabled.
  
   1: Enables the ALERT output pin
  
        mq8.setAlertPin(ALERT_PIN_DISABLE);       // Disables the ALERT output pin

5.Polarity: This bit configures the active level polarity of the ALERT output pin.

   0: Sets the ALERT pin to active low.
 
   1: Sets the ALERT pin to active high
 
        mq8.setPolarity(POLARITY_LOW);        // Sets the ALERT pin to active low
    
6.Hydrogen measurement:The following command is used to measure the Hydrogen value.

       mq8.Measure_Hydrogen(-1.44, 2.3);      // read the Hydrogen value
