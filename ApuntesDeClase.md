#  FACULTAD DE INGENIERIA MECANICA Y ELECTRICA - Pedro Andrés Castillo Gildo - Semestre 2 Grupo B - Ingenieria en computacion inteligente, Universidad de Colima
## PROGRAMACION ESTRUCTURADA Y ORIENTADA A OBJETOS, portafolio de diagramas y evidencias de codigos.
### Ejercicio 1.-
```dart
void main() {
  //instancia es creacion de un objeto a partir de la clase
  var e1 = Estudiante();
  Estudiante e2 = Estudiante();
  //esto se llama constructor porque esta construyendo la instancia e2 de la clase estudiante
  e1.nombre = "Pedro";
  e1.aNacimiento = 2004;
  e1.Reporte(2023);
  /* print(e1);
  print(e2); */
  e2.nombre = "Castillo";
  e2.aNacimiento = 2004;
  e2.Reporte(2023);

  /*  print(e1.nombre);
  print(e1.aNacimiento);
  print(e2.nombre);
  print(e2.aNacimiento); */
  // e1 y e2 son instancias
  // reutlizacion de codigo para evitar tener codigo duplicado
  /* reporte(e1);
  reporte(e2); */
}

class Estudiante {
  //todos los objetos tienen 2 cosas utilizables caracteristicas o atributos
  //comportamientos es lo que se puede hacer con los abijetos (indican accion)
  String nombre = ""; //Null y vacio son cosas distintas
  int? aNacimiento;

  void Reporte(int aActual) {
    print("Nombre: ${nombre}");
    print("Edad: ${aActual - aNacimiento!}");
  }
}

void reporte(Estudiante e) {
  print("Nombre: ${e.nombre}");
  print("Edad: ${2023 - e.aNacimiento!}");
}
 

//Clase animal, Atributos Nombre y Sonido
/* void main(List<String> args) {
  Animal perro = Animal();
  perro.nombre = "Firulais";
  perro.sonido = "Guau";
  perro.reporte();
  Animal gato = Animal();
  gato.nombre = "Minho";
  gato.sonido = "Miau";
  gato.reporte();
  Animal pato = Animal();
  pato.nombre = "Darwing";
  pato.sonido = "Cuak";
  pato.reporte()
  reporte(perro);
  reporte(gato);
  reporte(pato);
}

class Animal {
  String nombre = "";
  String sonido = "";
  //los metodos son todo lo que esta en una clase
  void reporte() {
    print("Nombre: ${nombre}");
    print("Sonido: ${sonido}");
  }
}

void reporte(Animal a) {
  print("Nombre: ${a.nombre}");
  print("Sonido: ${a.sonido}");
}
 */
```
 ### Diagrama de clase
![diagrama 19 03 23](https://github.com/PedroACG23/Parcial2sem2.md/assets/113472808/9cc9e5ce-4541-4a24-bd50-3db1c57d1d13)

## EJERCICIO 2.-
```dart
//import 'animal.dart';
/*import 'animal.dart';

void main(List<String> args) {
 // Animal a1 = new Animal();
  //Animal a2 = new Animal();
  /*print(a1);
  print(a2);*/

/*   a1.name = 'Perro';
  a1.sonido = 'Guau';
  a2.name = 'Gato';
  a2.sonido = 'Miau'; */

  Animal a3 = new Animal('Perro', 'Guau');

  print(a3.name);
  print(a3.sonido);
}*/
import 'animal.dart';
void main(List<String> args) {
  Persona P1 = new Persona('Florentino', 2000);

  print(P1.name);
  print(P1.aNac);
}

void getEdad(int aActual){
  print('La edad de ${this.name} es ${2023 - this.aNac!}');
}
/*class Animal{
  String? name;
  String? sonido;
  Animal(String name, String sonido){
    print('Constructor de Animal');
    this.name = name;
    this.sonido = sonido;
  }
}*/

class Persona{
  String? name;
  int? aNac;
  Persona(String name, int aNac){
    this.name = name;
    this.aNac = aNac;
  }
}
```
### Diagrama de clase
![diagrama 20 04 23](https://github.com/PedroACG23/Parcial2sem2.md/assets/113472808/e6bed289-8af2-4a7d-9f60-0cceed99a2cc)


## Ejercicio 3.-
```dart
/*Escriba un programa que tenga una clase Figura
Que tenga dos propiedades: base, altura
y dos metodos que calculen el area y el perimetro de un rectangulo
*/
import 'figura.dart';
void main(List<String> args) {
  Figura f1 = Figura.Rectangulo(4, 5);
  Figura f2 = Figura.cuadrado(4, 5);


  print('Area Rectangulo: ${f1.areaRectangulo()}');
  print('Area Cuadrado: ${f1.areaCuadrado()}');

  print('Area Rectangulo: ${f2.areaRectangulo()}');
  print('Area Cuadrado: ${f2.areaCuadrado()}');
}
class Figura{
  int? base;
  int? altura;

  //constructor

   /* Figura(int b, int a){
    base = b;
    altura = a;
  }*/

 /*  //constructor 2
  Figura(int base, int altura) {
    this.base = base;
    this.altura = altura;
  } */

  //constructor 3

    /*  Figura(this.base, this. altura); */

  //constructor 4

  /* Figura(int b, int a)
  : base = b,
  altura = a; */

  Figura.Rectangulo(this.base, this.altura);
  Figura.cuadrado(this.base, this.altura);

  int areaRectangulo() {
    return base! * altura!;
  }
  int areaCuadrado() {
    return base! * base!;
  }
}
```
### Diagrama de clase
![diagrama 26 04 23](https://github.com/PedroACG23/Parcial2sem2.md/assets/113472808/145cb243-f74d-463d-98cf-5a4331e8f24c)



## Ejercicio 4.- codigo 1:
```dart
import 'shape.dart';

void main(List<String> args) {
  Shape f1 = Shape(10, 5);
  print(f1.getArea());
  f1.base = 15;
  f1.altura = 10;
  print(f1.getArea());
  print('''El area del rectangulo 
  con base ${f1.base} y altura ${f1.altura} 
  es ${f1.getArea()}''');
}
class Shape {
  int? _base;
  int? _altura;

  Shape(this._base, this._altura);

  int getArea() {
    return _calcularArea();
  }

  int _calcularArea() {
    return _base! * _altura!;
  }
  /* void set base(int base) {
    _base = base;
  } */

  //setters
  void set base(int? base) => _base = base;
  void set altura(int? altura) => _altura = altura;
  //getters
  int? get base => _base;
  int? get altura => _altura;
}


//setters y getters set y get son metodos
```
### Codigo 2.-
```dart
import 'vehiculo.dart';

void main(List<String> args) {
  Vehiculo v1 = Vehiculo(
    'Toyota',
    'Corolla',
    'Rojo',
    'Automatico',
  );

  Vehiculo v2 = Vehiculo(
    'Honda',
    'Civic',
    'Azul',
    'Manual',
  );
  List<Vehiculo> vehiculos = [v1, v2];

  vehiculos.forEach((vehiculo) => vehiculo.showVehiculo());
}
class Vehiculo {
  String? _brand;
  String? _name;
  String? _color;
  String? _transmicion;

  Vehiculo(
    this._brand,
    this._name,
    this._color,
    this._transmicion,
  );

  void set brand(String brand) => this._brand = brand;
  void set name(String name) => this._name = name;
  void set color(String color) => this._color = color;
  void set transmicion(String transmicion) => this.transmicion = transmicion;

  String get brand => this.brand;
  String get name => this.name;
  String get color => this.color;
  String get transmicion => this.transmicion;

  void showVehiculo() {
    print(
      '''\n
      Marca: ${this._brand}
      Nombre: ${this._name}
      Color: ${this._color}
      Transmicion: ${this._transmicion}
      ''',
    );
  }
}
```

### Diagrama de clase
![diagrama27 04 23](https://github.com/PedroACG23/Parcial2sem2.md/assets/113472808/b65b0eb1-b46f-48d4-b4fe-d68111a0069e)

## Ejercicio 5.-
```dart
void main(List<String> args) {
  Animal a1 = Animal("Vaca", 10);
  a1.showAnimal();
  Animal.showAnimalStatic();
  print("-" * 28);
  Animal a2 = Animal("Cerdo", 20);
  a2.showAnimal();
  Animal.showAnimalStatic();
  List<Animal> animales = [a1, a2];
  int suma = 0;
  animales.forEach((element) {
    suma += element.cantidad;
  });
  print("Total de animales: $suma");
}

class Animal {
  //Propiedad de instancia
  String tipoAnimal;
  int cantidad;

  //Propiedad de clase
  static int counterStatic = 0;

  Animal(this.tipoAnimal, this.cantidad) {
    counterStatic++;
  }
  //Método de instancia
  void showAnimal() {
    print("Tipo de animal: $tipoAnimal");
    print("Cantidad: $cantidad");
  }

  // Metodo de clase
  static void showAnimalStatic() {
    print("Cantidad de tipos de animales: $counterStatic");
  }
}
```

### Diagrama de clase
![diagrama 3 05 23](https://github.com/PedroACG23/Parcial2sem2.md/assets/113472808/282b8ea1-322e-4194-beaa-ecd6d519e605)

## Ejercicio 6.-
```dart
import 'animal.dart';
import 'pato.dart';
import 'vaca.dart';
import 'caballo.dart';
void main(List<String> args) {
  Pato pato1 = Pato('Pekines', 10, "Curvo");
  pato1.showProperties();
  print("-" * 20);

  Animal a1 = Animal("Animal", 100);
  a1.showProperties();
  print("-" * 20);

  Vaca v1 = Vaca('Holstein', 30, 'Negro');
  v1.showProperties();
  print("-" * 20);

  Caballo c1 = Caballo('Azteca', 50, 'Negro');
  c1.showProperties();
  print("-" * 20);
}
class Animal {
  String? breed;
  int? quantity;

  Animal(this.breed, this.quantity);

  void showProperties() {
    print('Breed: $breed');
    print('Quantity: $quantity');
  }
}
import 'animal.dart';

class Caballo extends Animal {
  String? color_melena;

/*   Caballo(this.color_melena, String? breed, int? quantity)
  : super(breed, quantity); */
  Caballo(super.breed, super.quantity, this.color_melena);

  @override 
  void showProperties() {
    super.showProperties();
    print("Colode de melena: $color_melena");
  }

}

import 'animal.dart';

class Pato extends Animal {
  String? tipo_pico;

  Pato(super.breed, super.quantity, this.tipo_pico);
  
    @override 
    void showProperties() {
    super.showProperties();
    print("Tipo de pato: $tipo_pico");
  }
}
import 'animal.dart';

class Vaca extends Animal {
  String? color_manchas;
  
  Vaca(super.breed, super.quantity, this.color_manchas);

    @override 
  void showProperties() {
    super.showProperties();
    print("Color de manchas: $color_manchas");
  }

}
```

### Diagrama de clase
![diagrama 4 05 23](https://github.com/PedroACG23/Parcial2sem2.md/assets/113472808/55f5d10d-fc8b-4565-8691-af973f1cf6eb)

## Ejercicio 7.-
```dart
void main(List<String> args) {
  final vehiculo = Vehiculo('Rojo', 100);
  vehiculo.showVehiculo();
  print('Maxima velocidad: ${vehiculo.maxVelocidad()}');

  final Carro carro = Carro('Azul', 200, 'Toyota');
  carro.showVehiculo();
  print('Maxima velocidad: ${carro.maxVelocidad()}');

  final Carro carroTipo = Carro.tipo('Azul', 200, 'Toyota', 'Sedan');
  carroTipo.showTipo();
  print('---------');
  carroTipo.showTipo2();
  print('Maxima velocidad: ${carroTipo.maxVelocidad()}');
}


class Vehiculo {
  String? _color;
  int? _velocidad;

  Vehiculo(this._color, this._velocidad){
    print('Constructor padre Vehiculo');
  }

  set color(String? color) => this._color = color;
  set velocidad(int? velocidad) => this._velocidad = velocidad;

  String? get color => _color;
  int? get velocidad => _velocidad;

  int maxVelocidad() => _velocidad! *2;

  void showVehiculo(){
    print('Color: $_color');
    print('Velocidad: $_velocidad');
  }

}

class Carro extends Vehiculo{
  String? _marca;
  String? _tipo;

  Carro(super._color, super._velocidad, this._marca) {
    print('Constructor hijo Carro');
  }

    Carro.tipo(super._color, super._velocidad, this._marca, this._tipo) {
    print('Constructor nombrado tipo hijo Carro');
  }

  @override 
  void showVehiculo() {
    super.showVehiculo();
    print('Marca: $_marca');
  }

  void showTipo() {
    super.showVehiculo();
    print('Marca: $_marca');
    print('Tipo: $_tipo');
  }

  void showTipo2() {
    this.showVehiculo();
    print('Tipo: $_tipo');
  }
}
```

### Diagrama de clase
![diagrama 17 05 23](https://github.com/PedroACG23/Parcial2sem2.md/assets/113472808/95f8114d-9e04-4139-af08-75ca0b597d7f)

## Ejercicio 8.-
```dart
// Interfaces
// Interfaces are a way to define a contract on a class.
// Dart does not have syntax for declaring interfaces.
// Allowed code reutilization.
// Pretend simulate multiple inheritance.

void main(List<String> args) {
  ControlRemoto control = ControlRemoto();
  control.subirVolumen();
  control.bajarVolumen();

  Television tv = Television();
  tv.subirVolumen();
  tv.bajarVolumen();
}

class ControlRemoto {
  void subirVolumen() {
  }

  void bajarVolumen() {
  }
}

class Television implements ControlRemoto {
  @override 
  void subirVolumen() {
    print('Subier Volumen de la TV');
  }

  @override 
  void bajarVolumen() {
    print('Bajar Volumen de la TV');
  }
}
```

### Diagrama de clase
![diagrama 18 05 23](https://github.com/PedroACG23/Parcial2sem2.md/assets/113472808/5e9c67aa-2cdb-49f7-9f5c-df6e81e2b429)
