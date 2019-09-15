# Usando o digispark para exfiltrar dados do google chrome
this is a modified version from: https://github.com/cubidalsphere/Rubber-Ducky
you need to use https://github.com/mame82/duck2spark to encode digispark's payload

---

# vamos lá... 
pra começar vc precisa usar o duckencode e depois o duck2spark do mame82 (github mame82)

primeiro upa o arquivo referente à conexão com o gmail em algum free host... e configura ele tbm (né)

depois pega o payload .duck e usa o duckencoder (ta no git do mame82) nele:
cat ~/payload.duck | python duckencoder.py -p -l br > inject.bin

depois vc precisa usar o duck2spark (ta no git do mame82):
./duck2spark.py -i inject.bin -l 1 -f 2000 -o inject.ino

agora vc já tem o arquivo .ino é só subir pro digispark usando a IDE do arduino... (tem que baixar os drivers do digispark e tbm baixar a lib dele na ide do arduino)

se depois de tudo isso vc ainda não conseguir um payload funcional, esquece e vai estudar um pouco sobre arduino e HID antes de tentar isso...

[![VIDEO USANDO O DIGISPARK](https://static.makeuseof.com/wp-content/uploads/2015/12/youtube-player-670x335.jpg)](https://www.youtube.com/watch?v=py2dDVzWSw4)
