# CP4---Setup-FIWARE
# Descrição do projeto 📝
Este projeto utiliza um ESP32 para monitorar a luminosidade ambiente com um sensor LDR (fotoresistor) e controlar um LED onboard via MQTT. O código configura o ESP32 para se conectar a uma rede Wi-Fi, se conectar a um Broker MQTT, e publicar dados de luminosidade e o estado do LED.
# Funcionalidades
- Conexão com uma rede Wi-Fi.
- Conexão e autenticação com um Broker MQTT.
- Publicação do valor de luminosidade lido do sensor LDR em um tópico MQTT.
- Controle do LED onboard via MQTT.
- Recebimento de comandos MQTT para ligar ou desligar o LED onboard.
- Publicação do estado do LED em um tópico MQTT.
# Configuração
Variáveis Configuráveis

O código contém variáveis que podem ser ajustadas conforme necessário:

- default_SSID: Nome da rede Wi-Fi.
- default_PASSWORD: Senha da rede Wi-Fi.
- default_BROKER_MQTT: IP do Broker MQTT.
- default_BROKER_PORT: Porta do Broker MQTT.
- default_TOPICO_SUBSCRIBE: Tópico MQTT para receber comandos.
- default_TOPICO_PUBLISH_1: Tópico MQTT para publicar o estado do LED.
- default_TOPICO_PUBLISH_2: Tópico MQTT para publicar dados de luminosidade.
- default_ID_MQTT: ID para conexão com o Broker MQTT.
- default_D4: Pino do LED onboard (geralmente pino 2 no ESP32).
  # Hardware
- *ESP32 DEVKIT 1*
- *Sensor LDR (fotoresistor)*: Conectado ao pino 34 do ESP32.
- *LED onboard*: Utilizado para indicar o estado do LED (pino 2).
  # Conexões do Sensor LDR
- *VCC do fotoresistor-sensor* ao 3V3 do ESP32.
- *GND do fotoresistor-sensor* ao GND do ESP32.
- *A0 do fotoresistor-sensor* ao pino 34 do ESP32.
# Código
Funções Principais

- *initSerial()*: Inicializa a comunicação serial.
- *initWiFi()*: Conecta o ESP32 à rede Wi-Fi.
- *initMQTT()*: Configura o cliente MQTT.
- *setup()*: Configura o ambiente inicial e publica o estado inicial do LED.
- *loop()*: Função principal que executa as verificações e atualizações.
- *reconectWiFi()*: Conecta ou reconecta o ESP32 à rede Wi-Fi.
- *mqtt_callback()*: Função de callback para tratar mensagens recebidas via MQTT.
- *VerificaConexoesWiFIEMQTT()*: Verifica e reconecta o Wi-Fi e MQTT, se necessário.
- *EnviaEstadoOutputMQTT()*: Publica o estado atual do LED.
- *InitOutput()*: Inicializa o LED com um teste de piscar.
- *reconnectMQTT()*: Conecta ou reconecta o cliente MQTT ao Broker.
- *handleLuminosity()*: Lê o valor de luminosidade e o publica via MQTT.
  # Explicação do Código

1. *Inclusão das Bibliotecas*
   - #include <WiFi.h> e #include <PubSubClient.h>: Inclui bibliotecas necessárias para Wi-Fi e MQTT.

2. *Variáveis de Configuração*
   - Configura variáveis para o Wi-Fi, Broker MQTT e tópicos MQTT.

3. *Funções de Inicialização*
   - initSerial(), initWiFi(), e initMQTT() são responsáveis pela configuração inicial do serial, Wi-Fi e MQTT.

4. *Função setup()*
   - Inicializa o LED, a comunicação serial, a conexão Wi-Fi e MQTT. Publica o estado inicial do LED.

5. *Função loop()*
   - Verifica conexões e atualiza o estado do LED e dados de luminosidade.

6. *Funções de Conexão e Callback*
   - reconectWiFi(), mqtt_callback(), reconnectMQTT(): Funções para gerenciar a conexão Wi-Fi e MQTT, e tratar mensagens MQTT.

7. *Funções de Manipulação de Dados*
   - EnviaEstadoOutputMQTT(), handleLuminosity(): Publica o estado do LED e os dados de luminosidade no Broker MQTT.
# Link do CP 🔗
[https://wokwi.com/projects/396159048683156481](https://wokwi.com/projects/408107650851072001)
#  Componentes 🧠
|   Componente  |  Quantidade   |
| ------------- | ------------- |
|      resistores        |1 |
|      cabo macho/femea        | 3  |
|      ESP32        | 1  |
|      Módulo sensor fotoresistor        | 1 |
obs: na bancada foi usado o resistor
![image](https://github.com/user-attachments/assets/464961cb-dc87-4caf-81b6-aebcec0c7e49)

# Empresa 💎 
![image](https://github.com/Guig3003/CP2-Edge/assets/92872071/24cf31eb-4e21-49ea-884a-7e3153affd72)

Paulo Poças - RM556080;
Guilherme Gomes - RM554606;
Israel araujo henriques de Moura - Rm559068;
