**PT_BR**
Auxilio para para ativar Sensor DHT 11 ou 22 no RPi-Monitor no Raspberry Pi. RPI monitor RPi-Monitor: http://rpi-experiences.blogspot.com.br/

Primeiro certifique seu seu sensor esta operando siga este guia: https://www.filipeflop.com/blog/temperatura-umidade-dht11-com-raspberry-pi/

Testar o sensor,  use o script  para gerar os valores de temperatura: 
https://github.com/Lapidebr/RPi-Monitor-with-DHT-11-or-22/blob/master/rpi_dht11.py
Após testar o script neste formato 

*sudo /home/pi/rpi_dht11.py 11 25*

 onde 11 é tipo do seu sensor e 25 é pino GPIO correspondente, > [datasheet GPIO](https://www.raspberrypi.org/documentation/usage/gpio/README.md)
 
 O resultado gera um log em /var/log/dht11.log
para verificar o resultado use: cat /var/log/dht11.log o resultado deve ser neste formato: **Temp = 24 *C, Hum = 46 %**


Use cron  criar uma nova tarefa
*crontrab -e*
Crie uma tarefa*
*/1 * * * * sudo /home/pi/rpi_dht11.py 11 25*

*atenção ao  local onde salvou seu script
"rpi_dht11.py"


Configuração do arquivo da RPIMonitor para habilitar o sensor **/etc/rpimonitor/template/dht11.conf** 

Arquivo de exemplo aqui : https://github.com/Lapidebr/RPi-Monitor-with-DHT-11-or-22/blob/master/dht11.conf

Documento referencia: http://rpi-experiences.blogspot.com.br/2013/07/rpi-monitor-use-dht11-or-dht22-humidity.html

#DOCUMENTO AINDA NÃO FINALIZADO#

