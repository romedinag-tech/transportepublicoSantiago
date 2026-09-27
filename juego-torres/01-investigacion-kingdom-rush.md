# Nuestro juego de torres — Paso 1: qué es Kingdom Rush

Proyecto lúdico con Facundo (7 años): recrear **una etapa** al estilo *Kingdom Rush*, pero con **nuestras propias torres y armas**.

---

## 1. Qué es Kingdom Rush

- Juego de **defensa de torres** (*tower defense*) creado por **Ironhide Game Studio** (Uruguay) y publicado por Armor Games el **28 de julio de 2011**.
- Tiene secuelas: *Frontiers*, *Origins*, *Vengeance*, *Alliance* y otras.
- **La idea:** los enemigos avanzan por un **camino fijo** hacia la salida, que es tu reino. Tú construyes torres en **lugares marcados** junto al camino para detenerlos. Cada enemigo que llega a la salida te quita **una vida**.

## 2. Cómo se juega (el ciclo básico)

1. Empiezas con **oro** y **vidas** (normalmente 20).
2. Tocas un **lugar de construcción** vacío y eliges qué torre poner.
3. Los enemigos llegan en **oleadas**. Puedes llamar la siguiente oleada **antes de tiempo** y te dan oro extra por el apuro.
4. Cada enemigo derrotado te da **oro**, y con ese oro construyes o mejoras torres.
5. Si sobrevives a todas las oleadas, **ganas** y te dan **estrellas** (de 1 a 3, según cuántas vidas te quedaron).
6. Las estrellas se gastan en **mejoras permanentes** que sirven para las próximas etapas.

## 3. Las 4 torres clásicas

| Torre | Qué hace | Fuerte contra | Débil contra |
|---|---|---|---|
| 🏹 **Arqueros** | Disparan rápido, a larga distancia. Pueden darle a enemigos voladores. | Enemigos rápidos y voladores | Enemigos con armadura |
| 🛡️ **Cuartel** (*Barracks*) | Saca **3 soldados** que **bloquean el camino** y pelean cuerpo a cuerpo. Puedes mover el punto donde se juntan (*punto de reunión*). | Frenar a los enemigos para que las otras torres les peguen | Enemigos muy fuertes y voladores (no los alcanzan) |
| 🔮 **Magos** | Disparo lento pero muy fuerte, **atraviesa la armadura**. | Enemigos acorazados | Enemigos con resistencia mágica |
| 💣 **Artillería** | Bombas lentas que **explotan y dañan a varios** a la vez (daño en área). | Grupos grandes | Voladores (no los alcanza), enemigos sueltos y rápidos |

**Truco clave del juego:** el cuartel **frena** a los enemigos y la artillería o los magos les pegan mientras están quietos. Las torres se **combinan**.

### Mejoras de torres
- Cada torre sube de **nivel 1 → 2 → 3**.
- En el **nivel 4** eliges **uno de dos caminos**. Por ejemplo, los Magos pueden volverse:
  - **Mago Arcano:** rayo mágico y teletransporta enemigos hacia atrás.
  - **Hechicero:** invoca un gólem de tierra y debilita la armadura de los enemigos.
- Cada nivel 4 trae **habilidades especiales** que también se compran con oro.
- Puedes **vender** una torre y recuperar parte del oro.

## 4. Poderes especiales (hechizos)

Botones que usas cuando quieras y que después tienen un tiempo de espera (*recarga*):
- ☄️ **Lluvia de fuego:** caen meteoritos donde tú toques.
- ⚔️ **Refuerzos:** aparecen 2 soldados en el lugar que elijas.

## 5. Héroe

Un personaje especial que **tú mueves** por el mapa tocándolo. Pelea solo, sube de nivel y tiene poderes. Si muere, revive después de un rato.

## 6. Enemigos (y por qué hay que mezclar torres)

| Tipo | Ejemplo | Qué lo hace especial |
|---|---|---|
| Básico | Goblin | Débil y numeroso |
| Rápido | Lobo | Pasa corriendo |
| Acorazado | Orco con armadura | Las flechas y bombas le hacen poco daño → **usar magos** |
| Resistente a magia | Chamán | Los magos le hacen poco → **usar flechas/bombas** |
| Volador | Murciélago gigante | Se salta a los soldados y la artillería no lo alcanza → **usar arqueros/magos** |
| Jefe | Gigante | Mucha vida, llega al final de la etapa |

---

## 7. Lo que vamos a hacer nosotros (propuesta)

**Una sola etapa**, jugable en el navegador (computador o tablet), hecha con HTML + JavaScript, sin instalar nada.

### Lo que copiamos de Kingdom Rush
- Un camino con curvas y **6 a 8 lugares de construcción**.
- Oro, vidas y **8 a 10 oleadas** que se vuelven cada vez más difíciles.
- Botón para **llamar la oleada antes**.
- Torres con **3 niveles** de mejora.
- Un **poder especial** con recarga.

### Lo que inventamos nosotros 🎨
Las **torres**, las **armas**, los **enemigos** y el **escenario** los diseña Facundo. Para eso, cada torre se describe con esta ficha, y el juego la lee tal cual:

```
NOMBRE:        (ej: "Torre Lanzapiñas")
CÓMO SE VE:    (dibujo de Facundo, o color + emoji)
ARMA:          (qué dispara: flechas, rayos, bolas de nieve, pelotas...)
CUÁNTO CUESTA: (ej: 70 de oro)
DAÑO:          poco / medio / mucho
VELOCIDAD:     lenta / normal / rápida
ALCANCE:       corto / medio / largo
PODER ESPECIAL: (ej: congela, quema, empuja hacia atrás, le pega a varios)
¿LE PEGA A LOS QUE VUELAN?: sí / no
```

Y los enemigos con esta otra:

```
NOMBRE:       (ej: "Zombi Babosa")
CÓMO SE VE:
VIDA:         poca / media / mucha
VELOCIDAD:    lento / normal / rápido
¿VUELA?:      sí / no
¿ARMADURA?:   sí / no
ORO QUE DA:   (ej: 5)
```

### Ideas para empezar a imaginar (solo ejemplos)
- ❄️ **Torre de hielo:** lanza bolas de nieve que dejan lentos a los enemigos.
- 🐉 **Torre dragón:** echa fuego en línea.
- 🦖 **Cueva de dinosaurios:** en vez de soldados, sale un dinosaurio que bloquea el camino.
- 🌪️ **Torre ventilador:** empuja a los enemigos hacia atrás.

### Cómo lo vamos a construir (por etapas)
1. **Mapa y camino** — el escenario con el camino y los lugares para construir.
2. **Enemigos caminando** — que avancen por el camino y quiten vidas al llegar.
3. **Primera torre** — que dispare y derrote enemigos; oro al matar.
4. **Las torres de Facundo** — cargamos las fichas que él inventó.
5. **Oleadas, mejoras y poder especial.**
6. **Pantalla de ganar/perder con estrellas.** 🎉

Cada paso se puede probar jugando, así Facundo ve el avance y va cambiando cosas.

---

## Fuentes
- [Kingdom Rush — Kingdom Rush Wiki (Fandom)](https://kingdomrushtd.fandom.com/wiki/Kingdom_Rush)
- [Héroes de Kingdom Rush — Fandom](https://kingdomrushtd.fandom.com/wiki/Heroes/Kingdom_Rush)
- [Kingdom Rush — TV Tropes](https://tvtropes.org/pmwiki/pmwiki.php/VideoGame/KingdomRush)
- [Guía de torres — Steam Community](https://steamcommunity.com/sharedfiles/filedetails/?id=731318283)
- [Kingdom Rush en Armor Games](https://armorgames.com/play/12141/kingdom-rush)
