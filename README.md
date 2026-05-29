# UniFeob-PI
# 🎓 Smart Classroom - Arduino Uno

Sistema de monitoramento de presença para salas de aula utilizando sensores ultrassônicos HC-SR04 e Arduino Uno.

---

## 📖 Sobre o Projeto

O **Smart Classroom** é um protótipo de sala de aula inteligente desenvolvido com Arduino Uno. O sistema utiliza dois sensores ultrassônicos para detectar a presença de pessoas em diferentes áreas da sala.

Quando uma pessoa é detectada dentro da distância configurada (100 cm), LEDs indicadores são acionados para representar a ocupação daquela região.

Além disso, um LED central de status é ativado quando ambos os sensores detectam presença simultaneamente, indicando ocupação total da sala.

---

## 🚀 Funcionalidades

✅ Monitoramento de duas áreas independentes

✅ Detecção de presença utilizando sensores HC-SR04

✅ Indicação visual através de LEDs

✅ Monitoramento em tempo real pelo Serial Monitor

✅ LED de ocupação total da sala

✅ Estrutura pronta para expansão para IoT

---

## 🛠️ Componentes Utilizados

| Quantidade | Componente |
|-----------|------------|
| 1 | Arduino Uno |
| 2 | Sensor Ultrassônico HC-SR04 |
| 7 | LEDs |
| 7 | Resistores 220Ω |
| 1 | Protoboard |
| Diversos | Jumpers |

---

## 🔌 Esquema de Ligações

### Sensores

| Componente | Arduino |
|------------|----------|
| TRIG Sensor 1 | D3 |
| ECHO Sensor 1 | D4 |
| TRIG Sensor 2 | D6 |
| ECHO Sensor 2 | D5 |

### LEDs Sensor Esquerdo

| LED | Pino |
|------|------|
| LED_AL1 | D9 |
| LED_AC1 | D11 |
| LED_LZ1 | D7 |

### LEDs Sensor Direito

| LED | Pino |
|------|------|
| LED_AL2 | D8 |
| LED_AC2 | D10 |
| LED_LZ2 | D2 |

### LED Central

| LED | Pino |
|------|------|
| LED_LZ3 | D13 |

---

## ⚙️ Funcionamento

### Sensor Esquerdo

Quando a distância medida pelo Sensor 1 for menor ou igual a 100 cm:

```cpp
if (d1 <= 100)
```

Os LEDs:

- LED_AL1
- LED_AC1
- LED_LZ1

serão ligados.

---

### Sensor Direito

Quando a distância medida pelo Sensor 2 for menor ou igual a 100 cm:

```cpp
if (d2 <= 100)
```

Os LEDs:

- LED_AL2
- LED_AC2
- LED_LZ2

serão ligados.

---

### Ocupação Total da Sala

O LED central (LED_LZ3) será acionado apenas quando os dois sensores detectarem presença simultaneamente.

```cpp
if (digitalRead(led_lz1) == HIGH &&
    digitalRead(led_lz2) == HIGH)
{
    digitalWrite(led_lz3, HIGH);
}
```

---

## 📊 Monitor Serial

O sistema exibe continuamente as leituras dos sensores.

Exemplo:

```text
Sensor1: 57.3
Sensor2: 82.1
```

---

## 📂 Estrutura do Projeto

```text
Smart-Classroom/
│
├── README.md
├── SmartClassroom.ino
│
├── images/
│   ├── circuito.png
│   └── funcionamento.png
│
└── docs/
    └── relatorio.pdf
```

---

## 🔬 Lógica do Sistema

1. Os sensores HC-SR04 medem a distância até um objeto.
2. O Arduino processa os valores recebidos.
3. Caso a distância seja ≤ 100 cm:
   - Aciona os LEDs daquela região.
4. Caso ambos os sensores detectem presença:
   - Aciona o LED central.
5. Os dados são enviados ao Serial Monitor.

---

## 💡 Possíveis Melhorias

- Contagem automática de alunos.
- Controle inteligente de iluminação.
- Acionamento automático de ventiladores.
- Integração com ESP32.
- Dashboard Web.
- Registro de presença.
- Integração com banco de dados.
- Aplicativo para monitoramento remoto.

---

## 📚 Tecnologias Utilizadas

- Arduino IDE
- C/C++
- Arduino Uno
- HC-SR04
- Protoboard

---

## 👨‍💻 Autor

**Lucas Rocha**

Projeto desenvolvido para fins acadêmicos e estudos em automação, sistemas embarcados e Internet das Coisas (IoT).

---

## 📜 Licença

Este projeto está sob a licença MIT.

Sinta-se livre para utilizar, modificar e distribuir.
