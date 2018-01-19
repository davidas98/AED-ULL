# Programación Orientada a Objetos

Programación Orientada a Objetos (OOP)

## Clases

Una clase es una estructura que permite la descripción de las características (atributos) y comportamiento (métodos) de un conjunto de objetos. Las clases, al igual que muchos otros elementos de la OOP puede implementarse en casi cualquier lenguaje de programación. 

```c
struct struct_complex_t {

	double r_;
	double i_;
};

typedef struct struct_complex_t complex_t; 


void inicializa_complejo(complex_t* c, double r, double i)
{
	c->r_ = r;
	c->i_ = i;
}

void inicializa_complejo(complex_t* c)
{
	c->r_ = 0;
	c->i_ = 0;
}

void destruye_complejo(complex_t* c)
{
	c->r_ = 0;
	c->i_ = 0;
}

void imprime_complejo(complex_t* c)
{
	printf(" %3.1lf + %3.1lfi “, c->r_, c->i_);
}

void set_real(complex_t* c, double r)
{
	c->r_ = r;
}
	
void set_imag(complex_t* c, double i)
{
	c->i_ = i;
}

double get_real(complex_t* c)
{
	return c->r_;
}

double get_imag(complex_t* c)
{
	return c->i_;
}

double get_modulo(complex_t* c)
{
	return sqrt(c->r_ * c->r_ + c->i_ * c->i_);	
}

double get_fase(complex_t* c)
{
	return atan2(c->i_, c ->r_);	
}


complex_t suma(complex_t* c1,complex_t* c2)
{
	complex_t aux;

	aux.r_ = c1->r_ + c2->r_;
	aux.i_ = c1->i_ + c2->i_;

	return aux;
}

complex_t producto(complex_t* c1,complex_t* c2)
{
	complex_t aux;

	aux.r_ = c1->r_ * c2->r_ - c1->i_ * c2->i_;
	aux.i_ = c1->r_ * c2->i_ + c2->r_ * c1->i_ ;

	return aux;	
}


bool iguales(complex_t* c1,complex_t& c2)
{
	return (fabs(c1->r_ - c2->r_) < EPSILON) && (fabs(c1->i_ - c2->i_) < EPSILON);
}
```


