# *Padrão Bridge*

## 🔗 *Definição*
Desacopla uma abstração de sua implementação.

## 🎯 *Objetivo*
Permitir que abstração e implementação variem independentemente.

## 🧩 *Estrutura*
- Abstração
- Implementação
- Classes Concretas

## 💡 *Caso de Uso*
Controles remotos para diferentes dispositivos.

## ✅ Benefícios

- Separação de preocupações
- Extensibilidade
- Ocultação de detalhes de implementação

## 📝 *Exemplo em Java Explicação*
### Interface Dispositivo 
```java
interface Dispositivo {
    void ligar();
    void desligar();
}
```
Aqui, temos uma interface chamada Dispositivo, que define dois métodos:

- ligar(): para ligar o dispositivo.
- desligar(): para desligar o dispositivo.

Ela serve como contrato para qualquer classe que representar um dispositivo (como TV, rádio, etc.).

### Classe Abstrata ControleRemoto
```java
abstract class ControleRemoto {
    protected Dispositivo dispositivo;

    public abstract void ligarDispositivo();
    public abstract void desligarDispositivo();
}
```
A classe ControleRemoto é abstrata e tem um atributo protegido (dispositivo) do tipo Dispositivo, o que significa que ela pode controlar qualquer dispositivo que implemente a interface Dispositivo.

Ela possui dois métodos abstratos:

- ligarDispositivo(): método para ligar o dispositivo.
- desligarDispositivo(): método para desligar o dispositivo.

A ideia é que o ControleRemoto não precise saber como o dispositivo funciona internamente, ele apenas delega a ação ao dispositivo.
### Classe TV 
``` java
class TV implements Dispositivo {
    public void ligar() { 
        System.out.println("TV Ligada"); 
    }
    public void desligar() { 
        System.out.println("TV Desligada"); 
    }
}
```
A classe TV é uma implementação concreta da interface Dispositivo. Ela define os métodos ligar() e desligar() com comportamentos específicos para ligar e desligar a TV, respectivamente.
