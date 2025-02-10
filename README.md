# Projeto: Controle de LEDs e Display OLED com Raspberry Pi Pico

# Video: https://drive.google.com/file/d/17xKn5FF_NhvqQLNtuP5b2mO1ze4Sie9s/view

## Descrição

Este projeto implementa um sistema embarcado utilizando a placa **Raspberry Pi Pico**, que controla **LEDs**, um **display OLED SSD1306** e interage com entradas via **botões físicos** e **USB Serial**. O código permite:

- Acionar **LEDs** através de botões.
- Exibir mensagens no **display OLED** informando o estado dos LEDs.
- Receber **entrada via USB Serial** para exibir caracteres no **display OLED** e controlar uma matriz de LEDs via **PIO**.

---

## Hardware Utilizado

- **Raspberry Pi Pico**
- **Display OLED SSD1306 (I2C)**
- **LEDs** (verde e azul)
- **Botões** (A e B)
- **Resistores de pull-up internos**

---

## Configuração dos Pinos

| Componente | Pino | Função          |
| ---------- | ---- | --------------- |
| LED Azul   | 12   | Saída           |
| LED Verde  | 11   | Saída           |
| Botão A    | 5    | Entrada         |
| Botão B    | 6    | Entrada         |
| SDA (I2C)  | 14   | Comunicação I2C |
| SCL (I2C)  | 15   | Comunicação I2C |

---

## Dependências

O projeto utiliza as bibliotecas do **Pico SDK** para controle de GPIO, I2C e PIO, além das seguintes bibliotecas auxiliares:

- `lmatriz.h` - Controle da matriz de LEDs via PIO
- `num.h` - Manipulação de números na matriz
- `ssd1306.h` - Controle do display OLED SSD1306
- `font.h` - Fonte para exibição no display

---

## Funcionamento

### 1. Controle dos LEDs por botões

- **Botão A:** Alterna o estado do LED Verde e exibe "LED verde: ligado/desligado" no display.
- **Botão B:** Alterna o estado do LED Azul e exibe "LED azul: ligado/desligado" no display.
- Os botões possuem debounce por software (200ms).

### 2. Entrada via USB Serial

- Se um **número** for digitado via Serial, ele será exibido na matriz de LEDs e no display OLED.
- Se for **qualquer outro caractere**, os LEDs da matriz serão apagados e o caractere será exibido no display OLED.

### 3. Configuração do Display OLED

O display é inicializado e atualizado dinamicamente com base nas interações do sistema.

---

## Possíveis Melhorias

- Implementar um sistema de menus no display OLED.
- Criar animações na matriz de LEDs.
- Adicionar mais botões para outras funcionalidades.

---

## Autor

**Arthur** - Projeto para desenvolvimento embarcado com Raspberry Pi Pico W 2. 🚀
