[[Tema 9-Concurrencia en bases de datos]]
$\space$
Esperar-morir

W(A)
	W (B)
	W(A) -- rollback
W(B)

.
	W(A)
W(B)
W(A) -- espera
	W(B) -- rollback

Herir-esperar
W(A)
	W (B)
	W(A) -- espera
W(B) -- rollback

.
	W(A)
W(B)
W(A) -- rollback
	W(B)