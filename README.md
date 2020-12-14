## gsm library 
*	Author:     Nima Askari
*	WebSite:    https://www.github.com/NimaLTD
*	Instagram:  https://www.instagram.com/github.NimaLTD
*	LinkedIn:   https://www.linkedin.com/in/NimaLTD
*	Youtube:    https://www.youtube.com/channel/UCUhY7qY1klJm1d2kulr9ckw 
--------------------------------------------------------------------------------
* This library using my 'atc' library, please download 'http://github.com/nimaltd/atc'.
--------------------------------------------------------------------------------
* [x] NONE RTOS Supported.
* [x] RTOS V1 Supported.
* [x] RTOS V2 Supported.
--------------------------------------------------------------------------------
* [x] SIM800C tested.
* [ ] SIM800 tested.
* [ ] SIM800H tested.
--------------------------------------------------------------------------------   
* Enable USART (LL Library) and RX interrupt.
* Add library to your project.
* Configure `atcConfig.h` file.
* Create a struct as global.
* Create found callback function if you need it.
* Call `atc_init()`.
* You could add always search strings now.
* Call `atc_loop()` in infinit loop.
```
#include "atc.h"
atc_t  atc;

void  atc_found(char *foundStr)
{
  if (strstr(foundStr, "\r\n+CMD:") != NULL)
  {
  
  }
}

int main()
{
  atc_init(&atc, "MY_ATC", USART1, atc_found);
  atc_addSearch(&atc, "\r\n+CMD:");
  while (1)
  {
    atc_loop(&atc);
  }  
}
```



