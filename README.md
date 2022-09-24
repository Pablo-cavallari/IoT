# IoT
Repositório do curso de Iot + link do tikercad + código do circuito

Link:https://www.tinkercad.com/things/dkFyq5Vs1p1

// Sensor PIR

int pir = 13;
int valor = 0;

//Fotorresistencia
int pirLDR = 0;
int valorLDR=0;

//LEDs

int led1= 2;
int led2= 3;
int led3= 4;
int led4= 5;



void setup()
{
  // Configuração de Pinos.
  
  pinMode(pir, INPUT);
  pinMode(led1, OUTPUT);
  pinMode(led2, OUTPUT);
  pinMode(led3, OUTPUT);
  pinMode(led4, OUTPUT);
  
  //Configuração da Porta serial
  
  Serial.begin(9600);
  
}

void loop()
{
 //LEDs apagados, inicio do looping
  
  digitalWrite(led1, LOW);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
  
  valor= digitalRead(pir);
  valorLDR= analogRead(pirLDR);
  
  
  //Devolvendo o Valor lido
  
  Serial.println(valorLDR);
  
  if(valorLDR<910 && valor == HIGH) // SE Esta ativado
  {
  
  	digitalWrite(led1, HIGH); // LED vai acender
    digitalWrite(led2, HIGH); // LED vai acender
    digitalWrite(led3, HIGH); // LED vai acender
    digitalWrite(led4, HIGH); // LED vai acender
    
  }
  else{
  
    digitalWrite(led1, LOW); // LED vai apagar
    digitalWrite(led2, LOW); // LED vai apagar
    digitalWrite(led3, LOW); // LED vai apagar
    digitalWrite(led4, LOW); // LED vai apagar
  
  }
  delay(1000);
  
}
