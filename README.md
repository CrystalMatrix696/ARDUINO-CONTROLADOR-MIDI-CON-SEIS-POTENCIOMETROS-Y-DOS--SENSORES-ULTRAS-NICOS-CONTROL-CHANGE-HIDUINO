# ARDUINO-CONTROLADOR-MIDI-CON-SEIS-POTENCIOMETROS-Y-DOS-SENSORES-ULTRASÓNICOS-CONTROL-CHANGE-CONVERSION-HIDUINO
MIXER WITH 6 POTENCIOMETER´S AND 2 SENSOR ULTRASONIC MIDI USB, CONTROL CHANGE, HIDUINO PLUG AND PLAY MIDI INTERFACE.

---------------------------"UNIVERSIDAD NACIONAL AUTÓNOMA DE MÉXICO"---------------------------

AUTOR: BALANDRA SÁNCHEZ FRANCISCO JAVIER.

PROGRAMA ESPECIALIZADO: TECNOLOGÍA MUSICAL CON SOFTWARE LIBRE.

INTRUCCIONES.

Para ensamblar el controlador MIDI de seis potenciómetros y dos sensores ultrasónicos, necesitamos los 
siguientes materiales:
1. Dos sensores ultrasónicos; modelo HC-SR-04.
2. Cables tipo jumper´s, con puntas de conección de hembra hacia macho; por favor,
consulte las imagenes que se encuentran anexas en este repositorio, son diagramas para la instalación.
3. Seis potenciometros de 100 KOhms.
4. Cautín, pasta para soldar y soldadura de estaño.
5. Las imagenes de diagramas de este repositorio, las cuales se utilizarán como un mapa.

Para comenzar, dentro de los archivos anexados del repositorio se encuentran, una serie de imágenes, 
las cuales nos proporcionan la facilidad para realizar el ensamblado del controlador MIDI USB; además 
anexo una serie de instrucciones, para programar la tarjeta Arduino Uno y Mega.

Es un dispositivo MIDI, Plug and Play; es decir, al conectar el controlador MIDI directamente al 
ordenador, no será necesario instalar ningún programa o algún driver privativo o de uso libre, 
únicamente dentro del sistema se instala un driver genérico por defecto.Como sabemos la tarjeta 
Arduino Uno o Mega, se compone de entradas analógicas y digitales, las cuales nos permiten 
interactuar y dar instrucciones al microcontrolador; es decir, para que, Arduino realice dichas 
funciones. 

En la primera imagen del diagrama, imagen anexada al repositorio nos muestran del lado izquierdo 
6 potenciómetros, en la parte central de la imagen se ubica la tarjeta Arduino UNO, y del lado 
izquierdo se ubican los sensores ultrasónicos, los cuales tendrán la función similar que los 
potenciómetros, manipular parámetros enviando datos MIDI via USB.

Los cables de color negro representan la polaridad negativa, estos se conectan al PIN “GND”, 
denominada tierra; por otro lado, los cables de color rojo representan la polaridad positiva 
y conducen voltaje estos se conectan en el “PIN 5V”; es decir, conducen cinco voltios; sin 
embargo, se necesita conocer la polaridad de los potenciómetros, se muestra en la imagen del 
diagrama número dos; el potenciómetro tiene tres pines; por tanto, el pin denominado “tierra” 
está ubicado del lado izquierdo este se conecta al “PIN GND”, el pin central denominado 
“análogo”, el cual se conecta directamente a los pines analógicos de la tarjeta Arduino Uno 
o Mega; el pin denominado 5V, ubicado del lado derecho se conecta al PIN 5V de la tarjeta de 
Arduino. 

Cabe señalar, que el potenciómetro realiza la función de una resistencia, la cual es capaz de 
variar el flujo de voltaje; por tanto, el pin importante es el pin del centro, debido a que 
tiene la función de una resistencia variable, no importa en que pin siempre sea el cable positivo 
o negativo, izquierdo y derecho, es decir, en el caso, al instalar el cable de 5V en el pin 
izquierdo y GND en el derecho, o en su caso, el cable de 5v en el pin derecho  y GND  en el 
izquierdo, siempre que el pin central se instale en las entradas analógicas de la tarjeta 
Arduino.

Las entradas analógicas vienen marcadas en la placa de Arduino UNO o MEGA; en la placa Arduino UNO: 
A0, A1, A2, A3, A4, A5; en la placa Arduino MEGA: AO hasta A15; es decir, hace alusión que en 
la placa Arduino UNO se pueden conectar hasta seis potenciómetros, en las entradas analógicas y 
en la placa Arduino MEGA hasta 16 potenciómetros; cabe señalar, que se pueden ampliar dichos pines,
utilizando un multiplexor, para proyectos de mayor elaboración.

Cabe señalar, que la tarjeta Arduino UNO y MEGA, cuentan únicamente con tres pines marcado con el 
simbolo “GND” y un pin con el simbolo marcado "5V";  por tanto, en el caso de los seis potenciómetros 
sumando los dos sensores nos faltarían cinco pines “GND”, caso similar que se presenta con el PIN 5 V, 
y/o en casos de proyectos que involucren más sensores o potenciómetros; para solucionar, se utiliza 
un conector con dos salidas, el cual provee normalmente dos tornillos en la cabeza, este sirve para 
apretar los cables de un extremo y  otros cables del otro extremo, con otro tornillo, por lo que, 
estas puntas se deben soldar y se conectan al conector, con la finalidad, que únicamente provea un cable, 
para al PIN GND y otro cable sea proveído para el PIN 5v.

Para soldar los cables tipos jumpers, en la parte superior tienen una cubierta de plástico, ubica en 
los lados de la cubirta una entrada esta tiene normalmente un orificio y se puede visualizar un cuadro metálico, 
ingresa el alfiler en las esquinas de abajo, al hacer presión hacia arriba, se botará dicha cubierta, 
esto sirve, para retirar la cubierta, ajustar y soldar la entrada del cable al pin del potenciómetro, y después
para soldar las puntas de dicho cable de las puntas de los cables de otros potenciométros, es decir, este caso
aplica en los cables de los potenciometros para conectar a los pines GND y 5V, directamente a la placa Arduino, 
en los pines que sean exclusivos para las entradas analógicas y digitales, no se recomienda retirar la cubierta,
en la entrada macho.

Para finalizar, en el caso de los sensores ultrasónicos no es necesario soldar, al igual que los potenciometros,
sin embargo, es una herramienta facil de usar y para prototipos académicos o profesionales; por tanto, 
los cables jumper´s y la entrada al PIN  de la tarjeta Arduino, se pueden fijar utilizando una pistola 
de silicón, coadyuva para evitar que se desconecten los cables.

Los sensores ultrasónicos, en la parte trasera vienen rotulados, con los pines GND, VCC, ECHO, 
TRIG; El cable negro del PIN GND del sensor se conectan a los pines GND de la placa de Arduino Uno 
o Mega, y el cable de color rojo se conectan directamente en los pines VCC del sensor, se conectan 
al pin 5V de la placa Arduino; sin embargo, el “PIN TRIG” este se conectará al PIN ~5 y el 
“PIN ECHO” este se conectará al PIN 4, ambos pines se conectan en las entradas digitales, se pueden 
visualizar en las imágenes de los diagramas el cableado.

Para finalizar, el sensor ultrasónico número dos, el “PIN ECHO” se conecta al “PIN 7” de las 
entradas digitales de la placa Arduino UNO y/o MEGA; y el “PIN TRIG” este se conectará al “PIN ~6;
como puedes notar en ambos sensores los pines para TRIG o TRIGGER, siempre se conectarán algún 
pin de las entradas digitales que tengan el símbolo ~, es importante para que pueda funcionar dicho 
dispositivo del sensor, el cual envía un pulso ultrasónico y echo es el receptor, por tanto,en caso 
de conectar en otros pines los sensores el código viene con las instrucciones, para darle intrucción 
que pines reciben dicha información.

Para comenzar, se necesitan los programas LOOP MIDI, y Hairless-MIDI, Arduino IDE nos servirá
para cargar el siguiente código que se muestra a continuación, este código es para habilitar las
seis entradas analógicas de Arduino, y realizar un testeo de los potenciómetros; el siguiente código se 
conforma de tres partes, las cuales estan divididas con el simbolo (//------)estas partes están divididas,
con la denominación en el inicio y fin, void setup, inicio y fin y void loop, inicio y fin; primero descarga 
ARDUINO IDE, en caso que gustes utilizar el programa online Arduino Web Editor, lo puede buscar en 
google o utilizando el siguiente enlace: 


    https%3A%2F%2Fcreate.arduino.cc%2Feditor&usg=AOvVaw0fWpfesvgeGm3YLagOubXF  
    
    
    
 
 //NOTA DESDE AQUI, EMPIEZA EL CÓDIGO, COPIA Y PEGALO EN EL PROGRAMA DE ARDUINO IDE O EN PAGINA WEB ARDUINO WEB CREATE.
 //Carga el siguiente el siguiente Código en Arduino IDE o Arduino Web Editor:
 
 
 //---------------------------------------1.MIXER 6 POTS MIDI ABLETON, INICIO------------------------------------------------
int v0 = 0;
int v0_ = 0;
int v1 = 0;
int v1_ = 0;
int v2 = 0;
int v2_ = 0;
int v3 = 0;
int v3_ = 0;
int v4 = 0;
int v4_ = 0;
int v5 = 0;
int v5_ = 0;
int threshold = 2;
int int_to_midi_ratio = 1024 / 128;

void SendMidiToSerial (unsigned char word0, unsigned char word1, unsigned char word2) {
  Serial.write(word0);
  Serial.write(word1);
  Serial.write(word2);
}
//-----------------------------------------1.MIXER 6 POTS MIDI ABLETON, FINAL----------------------------------------------


void setup () {

  //-----------------------------------    1.MIXER 6 POTS MIDI ABLETON, VOID SETUP INICIO----------------------------------
  //Serial.begin(31250); // HIDUINO; FINAL, OJO QUITAR DIAGONALES PARA HABILITAR, ESTA OPCION O LA DE ABAJO.
  Serial.begin(57600); // PRUEBA O TEST

}
//----------------------------------------1.MIXER 6 POTS, MIDI ABLETON, VOID SETUP FINAL-----------------------------------


void loop () {

  //----------------------------------1.MIXER 6 POTS, MIDI ABLETON, VOID LOOP, INICIO--------------------------------------
  v0 = analogRead(0) / int_to_midi_ratio;
  v1 = analogRead(1) / int_to_midi_ratio;
  v2 = analogRead(2) / int_to_midi_ratio;
  v3 = analogRead(3) / int_to_midi_ratio;
  v4 = analogRead(4) / int_to_midi_ratio;
  v5 = analogRead(5) / int_to_midi_ratio;
  
  if (v0 - v0_ >= threshold || v0_ - v0 >= threshold) {
    v0_ = v0;
    SendMidiToSerial(176, 42, v0);
  }
  
  if (v1 - v1_ >= threshold || v1_ - v1 >= threshold) {
    v1_ = v1;
    SendMidiToSerial(176, 43, v1);
  }

  if (v2 - v2_ >= threshold || v2_ - v2 >= threshold) {
    v2_ = v2;
    SendMidiToSerial(176, 44, v2);
  }

    if (v3 - v3_ >= threshold || v3_ - v3 >= threshold) {
    v3_ = v3;
    SendMidiToSerial(176, 45, v3);
  }
  
  if (v4 - v4_ >= threshold || v4_ - v4 >= threshold) {
    v4_ = v4;
    SendMidiToSerial(176, 46, v4);
  }

  if (v5 - v5_ >= threshold || v5_ - v5 >= threshold) {
    v5_ = v5;
    SendMidiToSerial(176, 47, v5);
  }
  
}

//-----------------------------------------------1.MIXER 6 POTS, MIDI ABLETON, VOID LOOP, FIN-----------------------------------------------------------

//HASTA AQUI TERMINA EL CÓDIGO.------------------------------------------------------------------------



Una vez copilado el código dentro del programa de Arduino IDE, primero de nuevo dicho código y súbelo a la tarjeta Arduino UNO o MEGA, abre monitor en serie y
empieza girar cada uno de los potenciómetros, notarás que monitor en serie proporcionará una lectura con simbolos, letras y números; algunas veces monitor en 
serie puede contar con un retraso para las lecturas o en su caso, no realiza la lectura para solucionarlo, vuelve a renovar la ventana, es decir, cierra la ventana
y vuelve abrir la ventana de monitor en serie, asegurate que este calibradas las mediciones con el Baud Rate, asignado en el código.
Una vez, terminada la lectura puedes abrir Hairless MIDI y LOOP MIDI, mueve algún potenciometro y notarás que los leds del programa Hairless MIDI se encenderán,
abre el DAW o la Estacion de Audio Digital de tu agrado y mapa dichos potenciometros, notaras que empezarán a girar los potenciometros del instrumento virtual
o algún parámetro del secuenciador, o algúna función que hayas mapeado.

Posterior, abre otro nuevo sketch en el programa de Arduino IDE, empieza analizar el código anterior y el siguiente; notarás que el código siguiente ya cuenta con,
el código de los sensores ultrasónicos; por tanto, puedes copiarlo y pegarlo el siguiente código en el anterior, oara evitar perder las lecturas, es necesario 
copilarlo y subirlo en la placa de Arduino UNO y/o MEGA, aunque debes seguir las instrucciones del código y diagramas, primero instalar el código anterior y después
copiar y pegar el siguiente código , es con la finalidad al testear los potenciometros y sensores ultrasónicos, evitar que emergan inconvenientes en el 
retraso MIDI, y confusión de los valores de los potenciometros y los sensores ultrasónicos.



PRIMERO UBIQUE LA DIVISION DEL CÓDIGO “…---1. MIXER 6 POTS MIDI ABLETON, VOID SETUP INICIO---…; verifique que este activo el Baud Rate; es decir, que no tenga dos diagonales al inicio del comando, un ejemplo:
A)	ACTIVADO.
Serial.begin(31250); // HIDUINO; FINAL, OJO QUITAR DIAGONALES PARA HABILITAR, ESTA OPCION O LA DE ABAJO.
B)	 DESACTIVADO
//Serial.begin(31250); // HIDUINO; FINAL, OJO QUITAR DIAGONALES PARA HABILITAR, ESTA OPCION O LA DE ABAJO.

Es necesario mencionar, que únicamente actives una de las opciones que se describen en el código, se pueden subir dos instrucciones de BAUD RATE; sin embargo, es
para evitar problemas en las instrucciones del código y en la conversión del dispositivo en un dispositivo MIDI plug and play con HIDUINO, y también para evitar problemas de estabilidad del programa Hairless y LoopMIDI; una vez, instalado el código en la paca Arduino, abre Monitor serie y verifica que el Baud Rate del monitor se encuentre en 57600, empieza a girar los potenciómetros y notaras que otorga monitor en serie las lecturas, ahora selecciona el Baud Rate en 112500 y mueve los potenciometros , este paso es unicamente para los potenciometros; copia y pega el último código en el sketch anterior, copilarlo y subirlo o instalarlo en la tarjeta
Arduino UNO o MEGA, verifica el BAUD RATE EN 112500  y abre monitor en serie, notaras que otorga una lectura, acerca las manos al sensor y aleja; cierra monitor y sube de nuevo el código con el BAUD RATE en 31250, sigue las instrucciones HIduino al final.


Una vez, realizada las lecturas de los potenciómetros procedemos, en caso de no tener lectura en HIDUINO o HAIRLESS es complementar el código, es decir, instalaras de nuevo el código anterior, y el último será tu base, y de este código copiaras y pegaras en las divisiones de código que corresponda y como se muestra, en el último código, recuerdo que el primer código esta fusionado con el último, por tanto, el código maestro para seguir será el último, y  
será cortando pedazos del siguiente código y pegando en la división que corresponda sea INICIO, VOID SETUP, VOID LOOP.

Este código es el final, por tanto, antes de copiarlo y pegarlo, para dar rapidez lograrían perder el tiempo, porque sería un nuevo código, y los valores 
asignados y muestras tomadas por el Monitor en serie se perderían, es la razón, por la cual es necesario cortar el código y pegarlo, para evitar se pierdan los valores de los potenciómetros; por tanto, comienza pegando las divisiones del código 2 y 3, los cuales corresponden a los sensores ultrasónicos, al finalizar subelos directamente a la tarjeta Arduino.





//EMPIEZA CÓDIGO-------------
//----------------------------------------------1.MIXER 6 POTS MIDI ABLETON, INICIO-------------------------------------------------------------------------------
int v0 = 0;
int v0_ = 0;
int v1 = 0;
int v1_ = 0;
int v2 = 0;
int v2_ = 0;
int v3 = 0;
int v3_ = 0;
int v4 = 0;
int v4_ = 0;
int v5 = 0;
int v5_ = 0;
int threshold = 2;
int int_to_midi_ratio = 1024 / 128;
void SendMidiToSerial (unsigned char word0, unsigned char word1, unsigned char word2) {
  Serial.write(word0);
  Serial.write(word1);
  Serial.write(word2);
}
//---------------------------------1.MIXER 6 POTS MIDI ABLETON, FINAL------------------------------------------------------------------


//--------------------------------------------1. ULTRASONICO 2, ABLETON CONTROL CHANGE INICIO------------------------------------------
//Autor de los Códigos Daniel Marcial (@danielmarcial22); fusionador del código Francisco Javier Balandra Sánchez.

//Este código también funciona para controlar con la mano mientras el ultrasónico, puede permanecer recostado.
const int aMin = 5; //altura mínima a mapear
const int aMax = 50; //altura máxima a mapear
float distancia,distanciaAnterior;
long tiempo;
int valor;

//--------------------------------------------1. ULTRASONICO 2, ABLETON CONTROL CHANGE FINAL------------------------------------------

void setup () {

  //----------------------------------1.MIXER 6 POTS MIDI ABLETON, VOID SETUP INICIO--------------------------------------------------
  
  Serial.begin(31250); // HIDUINO; FINAL, OJO QUITAR DIAGONALES PARA HABILITAR, ESTA OPCION O LA DE ABAJO.
  //Serial.begin(57600); // PRUEBA O TEST.
//Serial.begin(112500); 

 pinMode(6, OUTPUT); // trigger, aqui arduino envia un pulso al sensor, para que inicie la medicion
 pinMode(7, INPUT);  // echo, con este arduino recibe el pulso cuyo tiempo representa
                       //la duracion del viaje del sonido en el aire.
 pinMode(5, OUTPUT); // trigger, aqui arduino envia un pulso al sensor, para que inicie la medicion
 pinMode(4, INPUT);  // echo, con este arduino recibe el pulso cuyo tiempo representa
                       //la duracion del viaje del sonido en el aire
}

//------------------------------------1.MIXER 6 POTS, MIDI ABLETON, VOID SETUP FINAL---------------------------------------------------


void loop () {
loopmixer ();
loopultra1 ();
loopultra2 (); 
}

void loopmixer () {

  //---------------------------------1.MIXER 6 POTS, MIDI ABLETON, VOID LOOP, INICIO--------------------------------------------------
  
  v0 = analogRead(0) / int_to_midi_ratio;
  v1 = analogRead(1) / int_to_midi_ratio;
  v2 = analogRead(2) / int_to_midi_ratio;
  v3 = analogRead(3) / int_to_midi_ratio;
  v4 = analogRead(4) / int_to_midi_ratio;
  v5 = analogRead(5) / int_to_midi_ratio;
  
  if (v0 - v0_ >= threshold || v0_ - v0 >= threshold) {
    v0_ = v0;
    SendMidiToSerial(176, 42, v0);
  }
  
  if (v1 - v1_ >= threshold || v1_ - v1 >= threshold) {
    v1_ = v1;
    SendMidiToSerial(176, 43, v1);
  }

  if (v2 - v2_ >= threshold || v2_ - v2 >= threshold) {
    v2_ = v2;
    SendMidiToSerial(176, 44, v2);
  }

    if (v3 - v3_ >= threshold || v3_ - v3 >= threshold) {
    v3_ = v3;
    SendMidiToSerial(176, 45, v3);
  }
  
  if (v4 - v4_ >= threshold || v4_ - v4 >= threshold) {
    v4_ = v4;
    SendMidiToSerial(176, 46, v4);
  }

  if (v5 - v5_ >= threshold || v5_ - v5 >= threshold) {
    v5_ = v5;
    SendMidiToSerial(176, 47, v5);
  }
  
} //OJO: CHECA ESTOSS SIMBOLOS AL FINAL DE CADA DIVISIÓN DEL CÓDIGO.

//-----------------------------------1.MIXER 6 POTS, MIDI ABLETON, VOID LOOP, FINAL------------------------------------------------------------


void loopultra1 () {


//--------------------------------------------2. ULTRASONICO 1, ABLETON CONTROL CHANGE, VOID LOOP, INICIO-------------------------------------
    //NOTA SIGUE LAS INSTRUCCIONES DEL CODIGO, VIENEN CON EL SIMBOLO (//) AL PRINCIPIO, O AL FINAL DEL CÓDIGO, PARA CONFIGURAR LOS PINES.
      digitalWrite(6,LOW); //EN EL PRIMER NÚMERO, ES EL PIN TRIGGER "TRIG" DEL SENSOR ULTRASÓNICO.
      delayMicroseconds(5);
      digitalWrite(6, HIGH); //Envio del pulso para iniciar medicion; EL PRIMER NÚMERO, ES EL PIN TRIG.
      delayMicroseconds(10); //Arduino espera 10 micro segundos.
      tiempo=pulseIn(7, HIGH);  //se mide la duración del pulso; EL PRIMER NÚMERO, ES EL PIN ECHO.
      distancia= 0.0177*tiempo; //multiplicamos el tiempo para convertirlo en dista
    
      if (abs(distanciaAnterior-distancia)>0.8) //resolución de 8 mm.
      {
        if (distancia<=aMax+2)
        {
        valor = map(distancia,aMin,aMax,0,127); //mapear alturas mínima y máxima a valores de 0 a 127  
        if (valor>127) valor=127; //limiter
        if (valor<0) valor=0; //limiter para los negativos
    Serial.write(177);//Control Change; selecciona el canal MIDI 1 =176; 2=177.
    Serial.write(30); // CC 30;número del control change; en este caso el sensor ultrasónico 1 utilizará el número 30, y el número 2, el número 31.
    Serial.write(valor); //CC value
    }
    distanciaAnterior = distancia;
  }

  delay(5);
  
}

  //--------------------------------------------2. ULTRASONICO 1, ABLETON CONTROL CHANGE, VOID LOOP, FINAL------------------------------------------/*

void loopultra2 () {


//--------------------------------------------3. ULTRASONICO 2, ABLETON CONTROL CHANGE, VOID LOOP, INICIO------------------------------------------
    
      digitalWrite(5,LOW); // PRIMER NUMERO ES EL PIN TRIGGER, PIN DE LA PLACA ARDUINO.
      delayMicroseconds(5);
      digitalWrite(5, HIGH); //envio del pulso para iniciar medicion //PRIMER NUMERO TRIGGER, PIN DE LA PLACA ARDUINO.
      delayMicroseconds(10); //arduino espera 10 micro segundos
      tiempo=pulseIn(4, HIGH);  //se mide la duración del pulso //ECHO; PRIMERO NUMERO, PIN DE LA PLACA ARDUINO.
      distancia= 0.0177*tiempo; //multiplicamos el tiempo para convertirlo en distancia.
    
      if (abs(distanciaAnterior-distancia)>0.8) //resolución de 8 mm.
      {
        if (distancia<=aMax+2)
        {
        valor = map(distancia,aMin,aMax,0,127); //mapear alturas mínima y máxima a valores de 0 a 127  
        if (valor>127) valor=127; //limiter, se aplica el limite maximo 127, para que no exceda dicho limite.
        if (valor<0) valor=0; //limiter; limite minimo 0.
    Serial.write(177);//Control Change canal 1 =176
    Serial.write(31); // CC 30 ; NUMERO DEL CONTROL CHANGE.
    Serial.write(valor); //CC value //El tipo de codificación o Código para procesar los datos MIDI, utilizará el sensor.
    }
    distanciaAnterior = distancia;
  }

  delay(5);
  
}

  //--------------------------------------------3. ULTRASONICO 2, ABLETON CONTROL CHANGE, VOID LOOP, FINAL------------------------------------------/*
  
 
 //-------------NOTA HASTA AQUI--------- TERMINA EL CÓDIGO.------------------
 
 
 
HIDUINO, CONVIERTE EL DISPOSITIVO PLUG AND PLAY.

 UNA VEZ ENSAMBLADO EL INSTRUMENTO SE PROCEDE A REALIZAR UNA PRUEBA TEST DE LOS POTENCIOMETROS Y LOS SENSORES ULTRASÓNICOS, UTILIZANDO ARDUINO IDE Y EL MONITOR EN SERIE, AL VERIFICAR EL ENVIO DE SEÑAL MIDI, SE PROCEDE A CARGAR EL CODIGO FINAL. ANTES DE INICIAR INSTALA EL PROGRAMA FLIP. 
1. SE ABRE EL CODIGO FINAL EN EL PROGRAMA ARDUINO IDE O ARDUINO WEB EDITOR ONLINE. 
2. ANTES DE CARGAR A LA TARJETA EL CÓDIGO, SE DEBE LOCALIZAR "VOID SETUP" UN COMMANDO DEL CODIGO, Y SELECCIONAR Serial.begin(57600) , POSTERIOR SE DEBE SUBIR EL ARCHIVO DIRECTAMENTE EN LA LA TARJETA ARDUINO. 
3. ABRIR EL MONITOR SERIE DEL PROGRAMA ARDUINO IDE, MOVER LOS POTENCIOMETROS; POSTERIOR SELECCIONA "Serial.begin(112500); COPIA Y PEGA EL CODIGO DESCRITO, CONFORME A LAS INSTRUCCIONES DESCRITAS ANTES, SUBELO A LA TARJETA Y EXCITAR LOS SENSORES ULTRASONICOS CON LAS MANOS U ALGÚN OBJETO, EL MONITOR SERIE AYUDA A MOSTRAR LOS DATOS MIDI Y LECTURAS.
4. CERRAR EL MONITOR EN SERIE, Y UBICAR EL COMANDO VOID SETUP, Y HABILITAR EL COMANDO "Serial.begin(31250), EVITAR CONTAR HABILITADOS DOS O MAS COMANDOS DE ESTE
TIPO, UNA VEZ TERMINADA LA CARGA DEL CODIGO, REALIZA LOS PASOS PARA ARDUINO HACIA HIDUINO. HAIRLESS MIDI Y LOOP MIDI, TE AYUDARAN DURANTE EL TESTEO DE LOS POTENCIOMETROS Y SENSORES ULTRASONICOS, Y UTILICES ALGUN DAW, 
PARA VERIFICAR EL ENVIO DE SEÑAL.

5. UNA VEZ CARGADO EL CODIGO, REALIZANDO LOS PASOS ANTERIORES, ABRE PANEL DE CONTROL Y DISPOSITIVOS E IMPRESOREAS DE WINDOWS 10, NOTARAS QUE DICE ARDUINO UNO O DISPOSITIVO COM4 O ALGUN NOMBRE; POR UN LADO, SE PROCEDE CON UN DESTORNILLADOR Y CON LA TARJETA CONECTADA, UBICAR LOS DOS PINES QUE ESTAN CERCA DEL CONECTOR USB DE LA TARJETA ARDUINO, SON LOS DOS PRIMEROS Y SE TOCAN CON EL DESTORNILLADOR, NOTARAS QUE SE APAGARÁ EL LED Y SE REINICIARÁ; DESCONECTA EL USB Y CONECTALO DE NUEVO, ABRE LA VENTANA DE DISPOSITIVOS E IMPRESORAS Y NOTARAS QUE CAMBIA EL NOMBRE DEL DISPOSITIVO, EN CASO QUE MENCIONE DISPOSITIVO DESCONOCIDO, NO IMPORTA REALIZA EL SIGUIENTE PASO. 
5.1. INSTALA FLIP, DIRIGITE A PANEL DE CONTROL Y DISPOSITIVOS, UBICA EL DISPOSITIVO DESCONOCIDO, DIRIGITE HACIA CONFIGURACION Y ACTUALIZAR CONTROLADOR, BUSCAR EL CONTROLADOR DENTRO DEL EQUIPO, EL DRIVER SE UBICA EN C://ARCHIVOS-DE-PROGRAMA-X86/Atmel/Flip ; Y SELECCIONA BUSCAR EN LA CARPETA FLIP, AL PRINCIPIO PUEDE COSTAR TRABAJO EN CASO QUE NO RECONOZCA, WINDOWS 10 BUSCAR LOS DRIVERS Y PUEDE TARDAR, AUNQUE ES UNA FORMA MÁS RÁPIDA Y SEGURA, ES LA RAZÓN, POR LA CUAL, SE PIDE INSTALAR FLIP AL INICIO, REINICIA EL ORDENADOR, VE DIRECTO EN PANEL DE CONTROL Y APARECERÁ COMO DISPOSITIVO ATMEL16U2.
UNA VEZ QUE APAREZCA EL DISPOSITIVO COMO ATMEL 16U2 Y NO APAREZCA COMO DISPOSITIVO DESCONOCIDO, INGRESA AL PROGRAMA FLIP, SELECCIONA EL ICONO DEL CHIP, SELECCIONA LA OPCION ATMEL16U2, CIERRA LA VENTANA Y SELECCIONA EL ICONO DEL CABLE Y SELECCIONA USB; NOTARAS QUE SE ACTIVAN LOS DEMÁS ICONOS, DESPUES SELECCIONA EL ICONO DEL LIBRO CON UNA FLECHA HACIA ABAJO, BUSCA EL ARCHIVO ARDUINO UNO HEX, DA CLICK EN EL ICONO RUN,DESCONECTA EL DISPOSITIVO USB, Y VUELVE A CONECTARLO DIRIGITE A PANEL DE CONTROL Y DISPOSITIVOS E IMPRESORAS, NOTARAS QUE CAMBIA AL NOMBRE DE DISPOSITIVO MIDI CON UN ICONO DE BOCINA, SI DESEAS REGRESARLO AL PUNTO DE INICIO, UNICAMENTE CLIKEA LOS PINES DE LA TARJETA, ABRE FLIP, REALIZA LOS PASOS ANTERIORES, Y AHORA SELECCIONA EL ARCHIVO ARDUINO UNO.HEX, DESCONECTA Y CONECTA EL US, REGRESARÁ EN EL ESTADO ANTERIOR.
INSTRUCCIONES RAPIDAS DE HIDUINO.
CARGADO EL CODIGO, VERIFICADO LOS POTENCIOMETROS Y SENSORES, DESPUES DE TOCAR LOS PINES QUE SE UBICAN EN LA TARJETA ARDUINO, CERCA DEL USB Y CAMBIO EL
NOMBRE DE DISPOSITIVO ATMEGA16U2, ABRE FLIP SELECCIONA EL ICONO DEL CHIP, SELECCIONA ATMEGA 16U2, SELECCIONA EL ICONO DEL CABLE, Y SELECCIONA USB, DESPUES SELECCIONA EL LIBRO CON FLECHA HACIA ABAJO Y SELECCIONA EL ARCHIVO HIDUINO.hex,, SELECCIONA ACEPTAR Y UBICA EL ICONO QUE DICE RUN, UNA VEZ CARGADO EL ARCHIVO, DESCONECTA EL USB DE ARDUINO Y CONECTALO DE NUEVO, LISTO APARACE COMO DISPOSITIVO MIDI PLUG AND PLAY, SE PUEDE VISUALIZAR EN PANEL DE CONTROL Y DISPOSITIVOS, HAZ UNA PRUEBA EN ABLETON U OTRO PROGRAMA Y LISTO.

EN CASO, QUE RECONOZCA EL DISPOSITIVO MIDI PLUG AND PLAY, PERO, NO RECONOZCA NINGUN SENSOR O POTENCIOMETROS, SE DEBE REALIZAR LOS PASOS DESDE EL PRINCIPIO, ANEXO //UNOS URLS DE LOS TUTORIALES, EL CODIGO Y MAS; ES MENESTER SEGUIR LAS INSTRUCCIONES.

//1.	Tutorial de Hiduino; Daniel Marcial; https://www.youtube.com/watch?v=oBItyubx5tI&list=LL3lT0HNcMEuT0c0f0wuFRvQ&index=486 2. Tutorial de Hiduino;
//2.	Instalar dispositivo midi plug and play y regresar al estado original la tarjeta Arduino; https://www.youtube.com/watch?v=Yd2OodoEuJc



 


