Este código foi desenvolvido para cumprir com os requisitos da atividade do capítulo 6 da unidade 4 do Embarcatech - CEPEDI. Seu objetivo é trabalhar interfaces de comunicação serial, mais especificamente os protocolos UART e I2C.

Ele foi desenvolvido para ser executado na placa de desenolvimento BitDogLab, que possui um microcontrolador Raspberry Pi Pico W (RP2040) e periféricos, como botões, matriz de LEDs WS2812, LED RGB e display SSD1306.

Suas funções incluem:
- Alternância do estado dos LEDs verde e azul, disparando uma mensagem no monitor serial e display;
- Envio de caracteres para o display através do monitor serial;
- Dado um caractere que seja um número entre 0 e 9, a exibição do mesmo também na matriz de LEDs.

Para comunicação com o monitor serial, utilizou-se o protocolo UART, enquanto para o display SSD1306, o protocolo I2C. A interação com os botões se deu através de rotinas de interrupção, recebendo também um tratamento de debouncing via software.

Como desafio, a atividade propôs a modificação da biblioteca **font.h** a fim de incluir letras do alfabeto minúsculas e qualquer outro caracteres especiais, para o qual foi escolhido unicamente o sinal de exclamação.
Essa biblioteca, em conjunto com a ssd1306, são necessárias para o funcionamento correto do display. Logo, qualquer caractere que não esteja devidamente configurado não será exibido e, neste código, os caracteres suportados são:
- Os números 0 a 9;
- Letras maiúsculas e minúsculas do alfabeto (A - Z) (a - z);
- O sinal de exclamação (!).

Para adicionar mais caracteres, deve-se colocar seus códigos hexadecimais em **font.h**, que exibe os números em 8x8 pixels, e realizar o tratamento na função **ssd1306_draw_char**, disponível em ssd1306.c, ambos na pasta _inc_.

Ressalta-se que, para apagar a matriz de LEDs, basta enviar um caractere suportado que não seja um número.

A seguir, há o link de um vídeo demonstrativo que exibe o funcionamento geral do código na BitDogLab:
[https://drive.google.com/file/d/1czKp_z4naHSxGsCnnclrMt3hYu87zKD1/view?usp=sharing]
