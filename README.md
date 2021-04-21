# linux-sound-fix-instruction
Инструкция для исправления проблем со звуком в ОС Ubuntu 20.04.2.0 LTS
1. Ввести в терминал команду sudo nano /etc/pulse/default.pa
2. Ввести пароль юзера
3. Раскоментировать следующие 6 строк:
load-module module-alsa-sink
load-module module-alsa-source device=hw:1,0
load-module module-oss device="/dev/dsp" sink_name=output source_name=input
load-module module-oss-mmap device="/dev/dsp" sink_name=output source_name=input
load-module module-null-sink
load-module module-pipe-sink
4. Сохранить файл
5. Затем в терминале ввести pulseaudio --k
6. В конце pulseaudio --start
