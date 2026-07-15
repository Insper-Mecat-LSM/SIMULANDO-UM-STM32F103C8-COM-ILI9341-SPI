# SIMULANDO-UM-STM32F103C8-COM-ILI9341-SPI

Autor: Hugo Lara Campos 

# Objetivo: 

Simulando um Chip STM32F103C8 com display ILI9341 SPI

## Softwares Necessário:

* STM32CubeIDE [link](https://www.st.com/en/development-tools/stm32cubeide.html)
* Proteus Labcenter [link](https://www.labcenter.com/)

## Introdução:

Nesse repósitorio será mostrado como simular o funcionamento de um display TFT ILI9841 no software Proteus Labcenter

## Configurações Iniciais:

Após abrir um novo projeto no CubeIDE, faça as configurações no CubeMX de acordo com a imagem abaixo, habilitando a conetividade SPI do chip em que estamos utilizando.

<img width="1916" height="1025" alt="Image" src="https://github.com/user-attachments/assets/a901b428-26b1-4f84-b1ca-a1394ebaf8cc" />

Realizando as configurações no CubeMX, volte para o CubeIDE e no arquivo **main.c** iremos escrever os primeiros textos. 

Na seção **Privates Includes** escreva:

```javascript
#include <string.h>
#include <stdarg.h>
#include "ili9341.h"
#include "ili9341_touch.h"
#include "fonts.h"
#include"testimg.h"
```

<img width="731" height="609" alt="Image" src="https://github.com/user-attachments/assets/50c0a6c6-8fe2-4b35-b15f-2affd74addd5" />

Todos esses arquivos já estão anexados nesse repositório, basta somente baixá-los.

Na seção **Private user code** escreva:

```javascript
void init() {
    ILI9341_Unselect();
    ILI9341_TouchUnselect();
    ILI9341_Init();
}

void loop() {

    // Check border
    ILI9341_WriteString(0, 3*10, "BEM VINDO", Font_11x18, ILI9341_WHITE, ILI9341_RED);
    ILI9341_WriteString(0, 6*10, "LAB SIST MECAT", Font_11x18, ILI9341_WHITE, ILI9341_RED);
    ILI9341_WriteString(0, 9*10, "INSPER", Font_11x18, ILI9341_WHITE, ILI9341_RED);
    ILI9341_WriteString(0, 12*10, "2026-2", Font_11x18, ILI9341_WHITE, ILI9341_RED);
    ILI9341_WriteString(0, 15*10, "ILI9341 SPI", Font_11x18, ILI9341_WHITE, ILI9341_RED);
/*
    ILI9341_DrawImage((ILI9341_WIDTH - 240) / 2, (ILI9341_HEIGHT - 240) / 2, 240, 240, (const uint16_t*)test_img_240x240);
    HAL_Delay(3000);
*/
}
```

<img width="1065" height="640" alt="Image" src="https://github.com/user-attachments/assets/e68ffa09-16da-48c4-85f1-ad74acf09028" />


