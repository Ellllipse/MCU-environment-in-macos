# MCU-environment-in-macos

## STM32 with Clion 

tool used:
- Clion
- STM32CubeMX

### Download Clion

Clion can be downloaded [here](https://www.jetbrains.com/clion/). This is a C/C++ IDE.

### Download STM32CubeMX

STM32CubeMX can be downloaded [here](https://www.st.com/en/development-tools/stm32cubemx.html). This is a graphical tool for easy configuration of the STM32 microcontroller. 

After a successful downloaded, open up a new terminal and type the following in the current folder:
```
sudo xattr -cr ~/SetupSTM32CubeMX-6.8.1.app
```

Then you can double click the "SetupSTM32CubeMX-6.8.1.app" to laund the wizard. In case of an error appear because of the fire wall setting, turn that off for now. 

### Other tools

Type the following in the terminal:

```
brew install open-ocd  
brew tap ArmMbed/homebrew-formulae
brew install arm-none-eabi-gcc
```

Then try if your gcc installed correctly: 

```
arm-none-eabi-gcc -v
```

## Here is a quick example of STM32 test project. 

1. Start a new project in Clion. Select the ".ioc" file and then click **"Open with STM32CubeMX"**.
2. STM32CubeMX will then be open, configure your board in the menu. I am using STM32F103C8T6, **Serial Wire** for Debugging mode, **Crystal** for high clock frequency with 72 MHz.
3. Then generate the code in the same folder of the project, with the same name.
4. Go back to the Clion, the folder content will be updated. I have used "st_nucleo_f103rb.cfg" as the broad config file. I have also modified the config file:

```
source [find interface /stlink-v2.cfg]
```

5. 
