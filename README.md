# tarea3
Figura Ate;
Figura Mariana;
Figura Haile;
Figura Selassie;
Figura Jah;
Figura Rastafari;
Figura Lion;
Figura Conqueror;

float apothem;
ArrayList <Figura> Figuras;

void setup() {
  size(700, 700);
  
  background(0);
  Ate= new Triangulo(5, 5, 5, 5, 5);
  Mariana= new Cuadrado(5);
  Haile= new Rectangulo(10, 5);
  Selassie= new Circulo(8);
  Jah= new Pentagono(10, 4);
  Rastafari= new Hexagono(10, 4);
  Lion= new Heptagono(10, 4);
  Conqueror= new Octagono(10, 4);
  Figuras = new ArrayList();
  Figuras.add(Ate);
  Figuras.add(Mariana);
  Figuras.add(Haile);
  Figuras.add(Selassie);
  Figuras.add(Jah);
  Figuras.add(Rastafari);
  Figuras.add(Lion);
  Figuras.add(Conqueror);
 
 
}

void draw() {
  
   int faces=0, centerx=0, centery=0, alto=0, ancho=0;

  noStroke();

  float angle=0;
  
  fill(0, 150, 20);
  pushMatrix();
  centerx=100;
  centery=200;
  ancho=50;
  angle=-90;
  alto=50;
  faces=3;
  poligon(faces, centerx, centery, ancho, alto, angle);
  popMatrix();

  pushMatrix();
  centerx=200;
  centery=200;
  angle=-45;
  ancho=50;
  alto=50;
  faces=4;
  poligon(faces, centerx, centery, ancho, alto, angle);
  popMatrix();
  
  pushMatrix();
  centerx=300;
  centery=200;
  angle=-45;
  ancho=100;
  alto=50;
  faces=4;
  poligon(faces, centerx, centery, ancho, alto, angle);
  popMatrix();

  pushMatrix();
  centerx=550;
  centery=200;
  angle=-90;
  ancho=80;
  alto=80;
  faces=5;
  poligon(faces, centerx, centery, ancho, alto, angle);
  alto=80;
  ancho=80;
  popMatrix();
  
  pushMatrix();
  centerx=450;
  centery=200;
  ellipse(centerx, centery, ancho, alto);
  popMatrix();

  pushMatrix();
  centerx=200;
  centery=400;
  angle=-90;
  ancho=80;
  alto=80;
  faces=6;
  poligon(faces, centerx, centery, ancho, alto, angle);
  popMatrix();

  pushMatrix();
  centerx=325;
  centery=400;
  angle=-90;
  ancho=80;
  alto=80;
  faces=7;
  poligon(faces, centerx, centery, ancho, alto, angle);
  popMatrix();
  
  pushMatrix();
  centerx=450;
  centery=400;
  angle=-90;
  ancho=80;
  alto=80;
  faces=8;
  poligon(faces, centerx, centery, ancho, alto, angle);
  popMatrix();


  println("Perimetro Ate(Triangulo):", Ate.perimetro());
  println("Area Ate:", Ate.area());

  println("Perimetro Mariana(Cuadrado):", Mariana.perimetro());
  println("Area Mariana:", Mariana.area());

  println("Perimetro Haile(Rectangulo):", Haile.perimetro());
  println("Area Haile:", Haile.area());

  println("Perimetro Selassie(Circulo):", Selassie.perimetro());
  println("Area Selassie:", Selassie.area());

  println("Perimetro Jah(Pentagono):", Jah.perimetro());
  println("Apotema", Jah.apothem());
  println("Area Jah:", Jah.area());

  println("Perimetro Rastafari(Hexagono):", Rastafari.perimetro());
  println("Apotema", Rastafari.apothem());
  println("Area Rastafari:", Rastafari.area());

  println("Perimetro Lion(Heptagono):", Lion.perimetro());
  println("Apotema", Lion.apothem());
  println("Area Lion:", Lion.area());

  println("Perimetro Conqueror(Octagono):", Conqueror.perimetro());
  println("Apotema", Conqueror.apothem());
  println("Area Conqueror:", Conqueror.area());
}



void poligon(float faces, float centerx, float centery, float ancho, float alto, float angle) {
  float angulo=360/faces;
  ancho=ancho/2;
  alto=alto/2;
  beginShape();
  for (int i=0; i<faces; i++) {
    vertex(centerx+ancho*cos(radians(angle)+radians(angulo*i)), centery+alto*sin(radians(angle)+radians(angulo*i)));
  }
  endShape();
}


interface Figura {
  float perimetro();
  float area();
  float apothem();
}
class Triangulo implements Figura {
  float f1, f2, c3, b, h;

  Triangulo(float b_, float h_, float f1_, float f2_, float c3_) {
    b=b_;
    h=h_;
    f1=f1_;
    f2=f2_;
    c3=c3_;
  }



  float perimetro() {
    return f1+f2+c3;
  }

  float area() {
    return ((b*h)/2);
  }
  float apothem() {
    return 0;
  }
  

}

class Cuadrado implements Figura {
  float l;

  Cuadrado(float l_) {
    l=l_;
  }




  float perimetro() {
    return l*4;
  }
  float area() {
    return l*l;
  }
  float apothem() {
    return 0;
  }
}

class Rectangulo implements Figura {
  float l, a;

  Rectangulo(float l_, float a_) {
    l=l_;
    a=a_;
  }

  float perimetro() {
    return (l*2)+(a*2);
  }
  float area() {
    return l*a;
  }
  float apothem() {
    return 0;
  }
}
class Circulo implements Figura {
  float r;

  Circulo(int r_) {
    r=r_;
  }

  float perimetro() {
    return (TWO_PI*r);
  }
  float area() {
    return (PI)*(r*r);
  }
  float apothem() {
    return 0;
  }
}
class Pentagono implements Figura {
  float f1, f2;

  Pentagono(float f1_, float f2_) {
    f1=f1_;
    f2=f2_;
  }




  float perimetro() {
    return (f1*5);
  }
  float apothem() {
    return sqrt((f1*f1)-(f2*f2));
  }
  float area() {
    float perimetro =f1*5; 
    float apothem= sqrt((f1*f1)-(f2*f2));

    return ((perimetro*apothem)/2);
  }
}
class Hexagono implements Figura {
  float f1, f2;

  Hexagono(float f1_, float f2_) {
    f1=f1_;
    f2=f2_;
  }




  float perimetro() {
    return f1*6;
  }
  float apothem() {
    return sqrt((f1*f1)-(f2*f2));
  }
  float area() {
    float perimetro =f1*6; 
    float apothem= sqrt((f1*f1)-(f2*f2));

    return ((perimetro*apothem)/2);
  }
}

class Heptagono implements Figura {
  float f1, f2;

  Heptagono(float f1_, float f2_) {
    f1=f1_;
    f2=f2_;
  }




  float perimetro() {
    return f1*7;
  }
  float apothem() {
    return sqrt((f1*f1)-(f2*f2));
  }
  float area() {
    float perimetro =f1*7; 
    float apothem= sqrt((f1*f1)-(f2*f2));

    return ((perimetro*apothem)/2);
  }
}

class Octagono implements Figura {
  float f1, f2;


  Octagono(float f1_, float f2_) {
    f1=f1_;
    f2=f2_;
  }




  float perimetro() {
    return f1*8;
  }
  float apothem() {
    return sqrt((f1*f1)-(f2*f2));
  }
  float area() {
    float perimetro =f1*8; 
    float apothem= sqrt((f1*f1)-(f2*f2));

    return ((perimetro*apothem)/2);
  }
}
