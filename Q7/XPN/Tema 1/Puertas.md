[[Tema 1-Modelado de procesos con BPMN]]

Lo normal es que en un proceso haya varias instancias en paralelo. Cada instancia es totalmente independiente de las demás, lo que pase en una no influye en las otras. 

```c
main() {
	doA();
	if(cond) {
		doB();
	} else {
		doC();
	}
	doD();
}
```

```c
main() {
	A();
	while(cond) {
		B();
	}
	C();
}
```

Es mala práctica resolver este bucle con una sola xor (2 entradas y 2 salidas). Para solucionarlo debemos utilizar 2 puertas xor.

La puerta xor no realiza trabajo, solo evalúa condiciones.

Las ramas de salida pueden llevar una condición asociada. Si no pueden salir por ninguna rama, el camino se queda parado. Los motores de automatización no comprueban que las condiciones sean excluyentes.