PT_BR
Documento refencia http://rpi-experiences.blogspot.com.br/2013/07/rpi-monitor-use-dht11-or-dht22-humidity.html

Auxilio para para ativar Sensor DHT 11 ou 22 no RPi-Monitor no Raspberry Pi. RPI monitor http://rpi-experiences.blogspot.com.br/
Primeiro certifique seu seu sensor esta operando siga este guia https://www.filipeflop.com/blog/temperatura-umidade-dht11-com-raspberry-pi/

Apos testar o sensor voce deve usar o script  para gerar os valores de temperatura 
https://github.com/Lapidebr/RPi-Monitor-with-DHT-11-or-22/blob/master/rpi_dht11.py
Após testar o script neste formato sudo /home/pi/rpi_dht11.py 11 25 
onde 11 é tipo do seu sensor e 25 é pino GPIO correpsondente. O resultado gera um log em /var/log/dht11.log
para verificar o resultado use: cat /var/log/dht11.log o resultado deve ser como este Temp = 24 *C, Hum = 46 %


Use cron  gerar uma nova tarefa
crontrab -e
Crie uma tarefa*
*/1 * * * * sudo /home/pi/rpi_dht11.py 11 25

*atenção ao  local onde salvou seu arquivo "rpi_dht11.py" 


Configuraçao do arquivo /etc/rpimonitor/template/dht11.conf 
https://github.com/Lapidebr/RPi-Monitor-with-DHT-11-or-22/blob/master/dht11.conf



#DOCUMENTO AINDA NÃO FINALIZADO#
