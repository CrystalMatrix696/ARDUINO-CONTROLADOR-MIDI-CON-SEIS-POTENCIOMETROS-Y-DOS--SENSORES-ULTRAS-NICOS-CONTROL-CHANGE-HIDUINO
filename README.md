# ARDUINO-CONTROLADOR-MIDI-CON-SEIS-POTENCIOMETROS-Y-DOS-SENSORES-ULTRASÓNICOS-CONTROL-CHANGE-CONVERSION-HIDUINO
MIXER WITH 6 POTENCIOMETER´S AND 2 SENSOR ULTRASONIC MIDI USB, CONTROL CHANGE, HIDUINO PLUG AND PLAY MIDI INTERFACE.

---------------------------"UNIVERSIDAD NACIONAL AUTÓNOMA DE MÉXICO"---------------------------

AUTOR: BALANDRA SÁNCHEZ FRANCISCO JAVIER.

PROGRAMA ESPECIALIZADO: TECNOLOGÍA MUSICAL CON SOFTWARE LIBRE.

INTRUCCIONES.

Para ensamblar el controlador MIDI, con seis potenciómetros y con dos sensores ultrasónicos, 
necesitamos contar con los siguientes materiales:
1. Dos sensores ultrasónicos; modelo HC-SR-04.
2. Cables tipo jumper´s, con puntas de conección de hembra hacia macho; por favor,
consulte las imagenes que se encuentran anexas en este repositorio, son diagramas para la instalación.
3. Seis potenciometros de 100 KOhms.
4. Cautín, pasta para soldar y soldadura de estaño.
Para comenzar, dentro de los archivos anexados del repositorio se encuentran, una serie de 
imágenes, las cuales nos proporcionan la facilidad para realizar el ensamblado del controlador 
MIDI USB; además anexo una serie de instrucciones, para programar la tarjeta Arduino Uno y Mega, 
Es un dispositivo MIDI, Plug and Play; es decir, al conectar el controlador MIDI directamente al 
ordenador, no será necesario instalar ningún programa o algún driver privativo o de uso libre, 
únicamente dentro del sistema se instala un driver genérico por defecto.
Como sabemos la tarjeta Arduino Uno o Mega, se compone de entradas analógicas y digitales, 
las cuales nos permiten interactuar y dar instrucciones ,para realizar que Arduino realice dichas 
funciones. En la primera imagen nos muestra del lado izquierdo 6 potenciómetros, en la parte central 
se ubica la tarjeta Arduino UNO, y del lado izquierdo se ubican los sensores ultrasónicos, 
los cuales tendrán la función similar que los potenciómetros, manipular parámetros enviando 
datos MIDI via USB.
Los cables de color negro representan la polaridad negativa, estos se conectan al PIN “GND”, 
denominada tierra; por otro lado, los cables de color rojo representan la polaridad positiva y 
conducen voltaje estos se conectan en el “PIN 5V”; es decir, conducen cinco voltios; sin embargo, 
se necesita conocer la polaridad de los potenciómetros, se muestra en la imagen del diagrama número 
dos; la perilla cuenta con tres pines, el pin denominado “tierra” ubicado del lado izquierdo se 
conecta al “PIN GND”, el pin denominado “análogo”, el cual se conecta directamente a los pines 
analógicos de la tarjeta Arduino Uno o Mega; el pin denominado 5V, ubicado del lado derecho se 
conecta al PIN 5V de la tarjeta de Arduino.
Las entradas analógicas vienen marcadas en la placa de Arduino UNO o MEGA; en la placa Arduino UNO: 
A0, A1, A2, A3, A4, A5; en la placa Arduino MEGA: AO hasta A15; es decir, hace alusión que en 
la placa Arduino UNO se pueden conectar hasta seis potenciómetros, y en la placa Arduino MEGA hasta 
16 potenciómetros.

Cabe señalar, que la tarjeta Arduino UNO y MEGA, cuentan únicamente con tres pines “GND”; por tanto, 
en el caso de los seis potenciómetros sumando los dos sensores nos faltarían cinco pines “GND”, 
caso similar que se presenta con el PIN 5 V, y/o en casos de proyectos que involucren más sensores 
o potenciómetros; para solucionar, se utiliza un conector con dos salidas, el cual provee 
normalmente dos tornillos en la cabeza, este sirve para apretar los cables de un extremo y  
otros cables del otro extremo, con otro tornillo, por lo que, estas puntas se deben soldar y se conectan al conector, 
con la finalidad, que únicamente provea un cable, para al PIN GND y otro para el PIN 5v.

Para soldar, los cables tipos jumpers en la parte superior tienen una cubierta de plástico, ubica en 
los lados una entrada esta tiene normalmente un cuadro metálico, ingresa el alfiler en las esquinas 
de abajo, al hacer presión se botará dicha cubierta, esto sirve para soldar las puntos despues al conectar el cable 
directamente a los pines de los potenciómetros, al quedar descubierta la punta del cable; este 
procedimiento se puede hacer en los dos extremos en el caso de los pines GND y 5V, en los pines 
que sean exclusivos para las entradas analógicas y digitales, no se recomienda retirar la cubierta,
en la entrada macho.

Para finalizar, en el caso de los sensores ultrasónicos no es necesario soldar, o en su caso 
que no quieran soldar, pueden utilizar una pistola de silicón para fijar, los cables tipo 
jumper´s directamente a los pines.

Los sensores ultrasónicos, en la parte trasera vienen rotulados, los pines con GND, VCC, ECHO, 
TRIG; los pines GND, se conecta al PIN GND de la placa de Arduino Uno o Mega, y los pines VCC se 
conectan al pin 5V de la placa Arduino; sin embargo, el “PIN TRIG” este se conectará al PIN ~5 y el 
“PIN ECHO” este se conectará al PIN 4, ambos pines se conectan en las entradas digitales, se pueden 
visualizar en las imágenes de los diagramas el cableado.
Para finalizar, el sensor ultrasónico número dos, el “PIN ECHO” se conecta al “PIN 7” de las 
entradas digitales; y el “PIN TRIG” este se conectará al “PIN ~6; como puedes notar en ambos 
sensores los pines para TRIG o TRIGGER, siempre se conectarán algún pin que tenga el símbolo ~, 
es importante para que pueda funcionar dicho dispositivo del sensor, el cual envía un pulso 
ultrasónico y echo es el receptor, por tanto,en caso de conectar en otros pines los sensores el
código viene con las instrucciones, para darle intrucción que pines reciben dicha información.

Para comenzar, se necesitan los programas LOOP MIDI, y Hairless-MIDI, estos nos servirán para 
realizar el testeo de los potenciómetros y sensores ultrasónicos; el siguiente código se conforma 
de tres partes, estas partes están divididas, en el inicio, void setup y void loop; primero descarga 
ARDUINO IDE, en caso que gustes utilizar el programa online Arduino Web Editor, lo puede buscar en 
google o utilizando el siguiente enlace: 
    https%3A%2F%2Fcreate.arduino.cc%2Feditor&usg=AOvVaw0fWpfesvgeGm3YLagOubXF  
 
 //Carga el siguiente el siguiente Código en Arduino IDE o Arduino Web Editor:
 
 
 //---------------------------------------1.MIXER 6 POTS MIDI ABLETON, INICIO-------------------------------------------------------------------------------
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
//-----------------------------------------1.MIXER 6 POTS MIDI ABLETON, FINAL-----------------------------------------------------------------------------------------


void setup () {

  //-----------------------------------    1.MIXER 6 POTS MIDI ABLETON, VOID SETUP INICIO---------------------------------------------------------------------------
  //Serial.begin(31250); // HIDUINO; FINAL, OJO QUITAR DIAGONALES PARA HABILITAR, ESTA OPCION O LA DE ABAJO.
  Serial.begin(57600); // PRUEBA O TEST

}
//----------------------------------------1.MIXER 6 POTS, MIDI ABLETON, VOID SETUP FINAL------------------------------------------------------------------------------


void loop () {

  //----------------------------------1.MIXER 6 POTS, MIDI ABLETON, VOID LOOP, INICIO------------------------------------------------------------------------------
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

HASTA AQUI TERMINA EL CÓDIGO.
Una vez cargado el código dentro del programa, copila dicho código y súbelo a la tarjeta Arduino UNO o MEGA, posteriormente dentro del código busca la división
del Código “…---1. MIXER 6 POTS MIDI ABLETON, VOID SETUP INICIO---…; verifique que este activo el Baud Rate  “Serial.begin(57600); //PRUEBA O TEST”, se verifica 
que no tenga dos diagonales ejemplo:
A)	ACTIVADO.
Serial.begin(31250); // HIDUINO; FINAL, OJO QUITAR DIAGONALES PARA HABILITAR, ESTA OPCION O LA DE ABAJO.
B)	 DESACTIVADO
//Serial.begin(31250); // HIDUINO; FINAL, OJO QUITAR DIAGONALES PARA HABILITAR, ESTA OPCION O LA DE ABAJO.

Es necesario mencionar, que únicamente actives una de las opciones, para evitar problemas en las instrucciones del código; una vez, subido a la paca Arduino el
código citado, abre Monitor serie y verifica que el Baud Rate del monitor se encuentre en 57060, empieza a girar los potenciómetros y notaras que otorga monitor en serie las muestras, ahora selecciona el Baud Rate en 112500 y mueve los potenciometros , este paso es unicamente para los potenciometros, posteriormente para los sensores se trabajara con este ultimo Baud Rate.
Una vez, realizada las lecturas de los potenciómetros procedemos, a complementar el código, esto 
será cortando pedazos del siguiente código y pegando en la división que corresponda sea INICIO, VOID SETUP, VOID LOOP.

Este código es el final, por tanto, antes de copiarlo y pegarlo, para dar rapidez lograrían perder el tiempo, porque sería un nuevo código, y los valores 
asignados y muestras tomadas por el Monitor en serie se perderían, es la razón, por la cual es necesario cortar el código y pegarlo, para evitar se pierdan los valores de los potenciómetros; por tanto, comienza pegando las divisiones del código 2 y 3, los cuales corresponden a los sensores ultrasónicos, al finalizar subelos directamente a la tarjeta Arduino.






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
//---------------------------------1.MIXER 6 POTS MIDI ABLETON, FINAL-----------------------------------------------------------------------------------------

//--------------------------------------------1. ULTRASONICO 2, ABLETON CONTROL CHANGE INICIO------------------------------------------
//Código hecho por Daniel Marcial (@danielmarcial22)

//Este código también funciona para controlar con la mano mientras el ultrasónico permanece recostado
const int aMin = 5; //altura mínima a mapear
const int aMax = 50; //altura máxima a mapear
float distancia,distanciaAnterior;
long tiempo;
int valor;

//--------------------------------------------1. ULTRASONICO 2, ABLETON CONTROL CHANGE FINAL------------------------------------------

void setup () {

  //---------------------------------------------------------------1.MIXER 6 POTS MIDI ABLETON, VOID SETUP INICIO---------------------------------------------------------------------------
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

//----------------------------------------------------------------1.MIXER 6 POTS, MIDI ABLETON, VOID SETUP FINAL------------------------------------------------------------------------------


void loop () {
loopmixer ();
loopultra1 ();
loopultra2 (); 
}

void loopmixer () {

  //------------------------------------------------------------1.MIXER 6 POTS, MIDI ABLETON, VOID LOOP, INICIO------------------------------------------------------------------------------
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

//-----------------------------------1.MIXER 6 POTS, MIDI ABLETON, VOID LOOP, FINAL------------------------------------------------------------------------------


void loopultra1 () {


//--------------------------------------------2. ULTRASONICO 1, ABLETON CONTROL CHANGE, VOID LOOP, INICIO------------------------------------------
    
      digitalWrite(6,LOW); 
      delayMicroseconds(5);
      digitalWrite(6, HIGH); //envio del pulso para iniciar medicion
      delayMicroseconds(10); //arduino espera 10 micro segundos
      tiempo=pulseIn(7, HIGH);  //se mide la duración del pulso
      distancia= 0.0177*tiempo; //multiplicamos el tiempo para convertirlo en dista
    
      if (abs(distanciaAnterior-distancia)>0.8) //resolución de 8 mm.
      {
        if (distancia<=aMax+2)
        {
        valor = map(distancia,aMin,aMax,0,127); //mapear alturas mínima y máxima a valores de 0 a 127  
        if (valor>127) valor=127; //limiter
        if (valor<0) valor=0; //limiter para los negativos
    Serial.write(177);//Control Change canal 1 =176
    Serial.write(30); // CC 30
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
      digitalWrite(5, HIGH); //envio del pulso para iniciar medicion //PRIMER NUMERO TRIGGER, PIN DE LA PLACA ARDUINO
      delayMicroseconds(10); //arduino espera 10 micro segundos
      tiempo=pulseIn(4, HIGH);  //se mide la duración del pulso //ECHO; PRIMERO NUMERO, PIN DE LA PLACA ARDUINO.
      distancia= 0.0177*tiempo; //multiplicamos el tiempo para convertirlo en dista
    
      if (abs(distanciaAnterior-distancia)>0.8) //resolución de 8 mm.
      {
        if (distancia<=aMax+2)
        {
        valor = map(distancia,aMin,aMax,0,127); //mapear alturas mínima y máxima a valores de 0 a 127  
        if (valor>127) valor=127; //limiter
        if (valor<0) valor=0; //limiter para los negativos
    Serial.write(177);//Control Change canal 1 =176
    Serial.write(31); // CC 30 ; NUMERO DEL CONTROL CHANGE.
    Serial.write(valor); //CC value
    }
    distanciaAnterior = distancia;
  }

  delay(5);
  
}

  //--------------------------------------------3. ULTRASONICO 2, ABLETON CONTROL CHANGE, VOID LOOP, FINAL------------------------------------------/*
  
  
 // UNA VEZ ENSAMBLADO EL INSTRUMENTO SE PROCEDE A REALIZAR UNA PRUEBA TEST DE LOS POTENCIOMETROS Y LOS SENSORES ULTRASÓNICOS, UTILIZANDO ARDUINO IDE Y EL MONITOR EN //SERIE, AL VERIFICAR EL ENVIO DE SEÑAL MIDI, SE PROCEDE A CARGAR EL CODIGO SYNTH FINAL. ANTES DE INICIAR INSTALA FLIP. 
//1. SE ABRE EL ARCHIVO SYNTH FINAL EN EL PROGRAMA ARDUINO IDE O ARDUINO WEB EDITOR ONLINE. 
//2. ANTES DE CARGAR A LA TARJETA EL CÓDIGO, SE DEBE LOCALIZAR "VOID SETUP" UN COMMANDO DEL CODIGO, Y SELECCIONAR Serial.begin(9600), POSTERIOR SE DEBE SUBIR EL //ARCHIVO //A LA TARJETA ARDUINO. 
//3. ABRIR EL MONITOR SERIE DEL PROGRAMA ARDUINO IDE, MOVER LOS POTENCIOMETROS Y EXCITAR LOS SENSORES ULTRASONICOS CON LAS MANOS U ALGÚN OBJETO, EL MONITOR SERIE //AYUDA A MOSTRAR LOS DATOS MIDI, TAL Y COMO SE VISUALIZA EN EL VIDEO. 
//4. CERRAR EL MONITOR EN SERIE, Y UBICAR EL COMANDO VOID SETUP, Y CAMBIAR "Serial.begin(31250), UNA VEZ TERMINADA LA CARGA DE NUEVO ABRIR EL MONITOR EN SERIE, Y //VERIFICAR QUE LOS SENSORES Y POTENCIOMETROS ENVIEN SEÑAL MIDI. 
//5. UNA VEZ CARGADO EL CODIGO, REALIZANDO LOS PASOS ANTERIORES, ABRE PANEL DE CONTROL Y DISPOSITIVOS E IMPRESOREAS, NOTARAS QUE DICE ARDUINO UNO O DISPOSITIVO COM4 O //ALGUN NOMBRE; POR UN LADO, SE PROCEDE CON UN DESTORNILLADOR Y CON LA TARJETA CONECTADA, UBICAR LOS DOS PINES QUE ESTAN CERCA DEL CONECTOR USB DE LA TARJETA ARDUINO, //SON LOS DOS PRIMEROS Y SE TOCAN CON EL DESTORNILLADOR; ABRE LA VENTANA DE DISPOSITIVOS E IMPRESORAS Y NOTARAS QUE CAMBIA EL NOMBRE DEL DISPOSITIVO EN CASO QUE //MENCIONE DISPOSITIVO DESCONOCIDO, NO IMPORTA REALIZA EL SIGUIENTE PASO. 
//5.1. INSTALA FLIP, DIRIGITE A PANEL DE CONTROL, UBICA EL DISPOSITIVO DESCONOCIDO, CONFIGURACION Y ACTUALIZAR CONTROLADOR, BUSCAR EL CONTROLADOR DENTRO DEL EQUIPO, //UBICA ARCHIVOS DE PROGRAMA X86/Atmel/Flip ; Y SELECCIONA BUSCAR, AL PRINCIPIO PUEDE COSTAR TRABAJO EN CASO QUE NO RECONOZCA, WINDOWS 10 BUSCAR LOS DRIVERS Y PUEDE //TARDAR, AUNQUE ES UNA FORMA MÁS RÁPIDA Y SEGURA, ES LA RAZÓN, POR LA CUAL, SE PIDE INSTALAR FLIP AL INICIO, EN CASO QUE NO RECONOZCA SEGUIR LOS PASOS ANTES //MENCIONADOS. 
//UNA VEZ QUE APAREZCA EL DISPOSITIVO COMO ATMEL 16U2 Y NO APAREZCA COMO DISPOSITIVO DESCONOCIDO, INGRESA AL PROGRAMA FLIP, SELECCIONA EL ICONO DEL CHIP, SELECCIONA //ATMEL16U2, SELECCIONA EL ICONO DEL CABLE Y SELECCIONA USB; DESPUES SELECCIONA EL ICONO DEL LIBRO CON UNA FLECHA HACIA ABAJO, BUSCA EL ARCHIVO ARDUINO UNO HEZ, CON //ESTO REGRESA AL ESTADO ORIGINAL, DIRIGITE A PANEL DE CONTROL Y DISPOSITIVOS E IMPRESORAS, NOTARAS QUE CAMBIA EL NOMBRE DEL DISPOSITIVO, DESCONECTA Y CONECTA EL USB //Y ABRE ARDUINO IDE, Y REALIZA LOS PASOS DESDE EL INICIO.
//CARGADO EL CODIGO, VERIFICADO LOS POTENCIOMETROS Y SENSORES, DESPUES DE TOCAR LOS PINES QUE SE UBICAN EN LA TARJETA ARDUINO, CERCA DEL USB Y CAMBIO EL //NOMBRE DE //DISPOSITIVO ATMGEA16U2, ABRE FLIP SELECCIONA EL ICONO DEL CHIP, SELECCIONA ATMEGA 16U2, SELECCIONA EL ICONO DEL CABLE, Y SELECCIONA USB, DESPUES SELECCIONA EL LIBRO //CON FLECHA HACIA ABAJO Y SELECCIONA EL ARCHIVO HIDUINO.hex,, SELECCIONA ACEPTAR Y UBICA EL ICONO QUE DICE RUN, UNA VEZ CARGADO EL ARCHIVO, DESCONECTA EL ARDUINO Y //CONECTALO, LISTO APARACE COMO DISPOSITIVO MIDI PLUG AND PLAY, SE PUEDE VISUALIZAR EN PANEL DE CONTROL Y DISPOSITIVOS, HAZ UNA PRUEBA EN ABLETON U OTRO PROGRAMA Y //LISTO.

//EN CASO, QUE RECONOZCA EL DISPOSITIVO MIDI PLUG AND PLAY, PERO, NO RECONOZCA NINGUN SENSOR O POTENCIOMETROS, SE DEBE REALIZAR LOS PASOS DESDE EL PRINCIPIO, ANEXO //UNOS URLS DE LOS TUTORIALES, EL CODIGO Y MAS.

//1.	Tutorial de Hiduino; Daniel Marcial; https://www.youtube.com/watch?v=oBItyubx5tI&list=LL3lT0HNcMEuT0c0f0wuFRvQ&index=486 2. Tutorial de Hiduino;
//2.	Instalar dispositivo midi plug and play y regresar al estado original la tarjeta Arduino; https://www.youtube.com/watch?v=Yd2OodoEuJc



 


