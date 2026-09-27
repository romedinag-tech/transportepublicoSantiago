# Etapa 1 — La cascada del tigre

Diseño inventado por Facundo. El juego jugable está en [`juego.html`](juego.html): se abre con doble clic en cualquier navegador.

## El escenario
Una pradera con árboles, flores y una **cascada** arriba. El río baja desde la cascada y cruza el camino por un **puente**. Los enemigos entran por una cueva a la izquierda y quieren llegar al **castillo** de la derecha.

## Enemigos

| Enemigo | Qué hace | Su debilidad |
|---|---|---|
| 🐅 **Gran Tigre del Río** | Baja nadando desde la cascada. Lanza **bolas de agua** que mojan las torres y las dejan 3 segundos sin disparar. Si llega al final del río, quita 3 vidas. | **Nunca sale del río**: hay que poner arqueros cerca del agua. |
| 🛸 **Nave espacial** | Baja del cielo, aterriza y suelta 3 aliens. | Si la derribas antes de que los suelte, los que quedan no salen. |
| 👽 **Alien torpe** | Muy fuerte, golpea duro a los soldados. | Camina lentísimo y **se tropieza** en la tierra (se cae y queda quieto un rato). |
| 🦖 **Ave de fuego** (prehistórica) | Vuela sobre el camino y lanza **bolas de fuego** que queman las torres o hieren a los soldados. | Tiene poca vida. |
| 🦅 **Ave de garras** | **Agarra a un soldado**, lo sube y lo suelta desde el aire. | Si la derribas mientras lo lleva, el soldado se salva. No puede agarrar a los que están en el refugio. |

## Torres

| Torre | Qué hace | Niveles |
|---|---|---|
| 🏹 **Arqueros** | Disparan a todo: aliens, aves, naves y al tigre. | Nivel 3: **flechas de fuego** que dejan quemando. |
| 🛡️ **Cuartel** | Saca 3 soldados que bloquean el camino. Se puede mover su bandera. | Soldados con más vida y fuerza. |
| 📡 **Radar** | Avisa qué enemigos vienen en la próxima oleada y marca **dónde aterrizará la nave**. Los arqueros cercanos disparan más lejos. | Más alcance y más ayuda. |
| 🏠 **Refugio** | Los soldados **se guarecen** ahí: se curan y las aves no los agarran. Va **juntando fuerza**; cuando está llena, se libera una onda que golpea a los enemigos y los soldados pegan el doble por 10 segundos. | Junta fuerza más rápido y golpea más fuerte. |

## Cómo cambiar el juego
Al comienzo del código de `juego.html` están las fichas `TORRES`, `ENEMIGOS` y `OLEADAS`. Se pueden cambiar vidas, velocidades, daños, precios y cuántos enemigos trae cada oleada.

## Ideas para la próxima versión
- Un **héroe** que se mueva por el mapa (¿quién sería?).
- Sonidos: el rugido del tigre, el zumbido de la nave.
- Una segunda etapa (¿el bosque, la montaña, el espacio?).
- Dibujos de Facundo escaneados como imágenes de las torres y enemigos.
