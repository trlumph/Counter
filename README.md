# Lab 5: STM LED Binary Counter
### Author: Tymur Krasnianskyi
### Description: 
Implemented a binary LED counter where an increment is triggered by a button push.

### Parts used:
- 1x STM32F411E-DISCO
- 1x Bread board
- 7x Resistors 150 Ohm
- 1x Resistor 220K Ohm
- 10x Wires 
- 1x Button
- 6x Blue LEDs

### Video demo:
https://drive.google.com/file/d/1LLEaVHBt59IzZCWvmxopj7p0EjtMcl0p/

### IOC Setup:
- Pins PE7-PE12 Dedicated for GPIO Output (6 external LEDs)
- Pin PA1 and VDD Dedicated for the button (GPIO Input)

### Bouncing resolution:
- Busy loop
```
if(HAL_GPIO_ReadPin(GPIOA, GPIO_PIN_1) == GPIO_PIN_SET){
    ++counter;
    HAL_Delay(50);
    while(HAL_GPIO_ReadPin(GPIOA, GPIO_PIN_1) == GPIO_PIN_SET){ }
    HAL_Delay(50);
}
```


### Suspension resistors
This is done in order to protect the board from short circut in case button is setup as output.


### Images:
![](https://i.imgur.com/VVoFsb0.jpg)
![](https://i.imgur.com/SHdHcJe.jpg)
![](https://i.imgur.com/hxkmv5o.jpg)