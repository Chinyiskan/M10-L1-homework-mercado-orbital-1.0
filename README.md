# MO-102 · Mercado Orbital: oferta relámpago y hora de la estación

**Asignado por:** Nova
**Dónde trabajas:** en tu Mercado Orbital de la clase (con los tickets de hoy resueltos)
**Tiempo estimado:** entre 40 y 50 minutos
**Puntaje:** 15 puntos

Nova quiere que el puesto se sienta vivo: una oferta con cuenta regresiva y la hora de la estación en el encabezado. Las dos cosas pasan con el tiempo, así que cada una lleva su `useEffect` con su cleanup. Los estilos ya están en `App.css`: solo usa las clases que se indican.

## Ticket 1 · Oferta relámpago (6 puntos)

Crea `src/components/OfertaRelampago.jsx` y muéstralo en `App.jsx` entre la bienvenida y el catálogo.

- Un estado `segundos` que empieza en 60.
- Mientras `segundos` sea mayor que 0, muestra:
  `<section className="oferta">` con el texto "Oferta relámpago: Propulsor turbo a 450 cr" y un `<span className="cuenta">` con "Termina en 60 s" (el número real).
- Cuando llegue a 0, muestra `<section className="oferta oferta-terminada">` con "La oferta del Propulsor turbo terminó."

Estructura para arrancar:

```jsx
import { useState, useEffect } from "react";

function OfertaRelampago() {
    const [segundos, setSegundos] = useState(60);

    useEffect(() => {
        // 1. Si segundos ya es 0, return (la cuenta se detiene).
        // 2. Un setTimeout de 1000 ms que baje segundos en 1.
        // 3. Cleanup con clearTimeout.
    }, [/* ¿qué valor lee el efecto? */]);

    // Aquí el if para cuando la oferta terminó, y luego el return normal.
}

export default OfertaRelampago;
```

**Listo cuando:** la cuenta baja de a un segundo (no de a dos) y al llegar a 0 aparece el mensaje de oferta terminada.

## Ticket 2 · Hora de la estación (5 puntos)

Crea `src/components/RelojEstacion.jsx` y ponlo dentro de `Encabezado.jsx`, debajo del subtítulo.

- Un estado `hora` que empieza en `new Date()`.
- Un efecto con `setInterval` cada 1000 ms que actualiza `hora` con `new Date()`, y su cleanup con `clearInterval`.
- Muestra `<p className="reloj">Hora de la estación: {hora.toLocaleTimeString()}</p>`.

**Listo cuando:** la hora avanza sola cada segundo.

## Ticket 3 · Prueba en consola (4 puntos)

1. En el efecto del reloj pon `console.log("Reloj encendido")` y en el cleanup `console.log("Reloj apagado")`.
2. Recarga la página y mira la consola.
3. Al final de este README, en una sección **"Lo que vi en la consola"**, escribe qué mensajes salieron, en qué orden y por qué (dos o tres líneas).
4. Borra los dos `console.log`: la consola debe quedar limpia.

## Extra (sin puntos)

Mientras la oferta esté activa, la tarjeta del Propulsor turbo muestra 450 cr y se agrega al carrito a ese precio. Cuando termina, vuelve a 640 cr. Pista: el estado `segundos` tendría que subir a `App` para que la tarjeta y la oferta lo compartan.

## Entrega

Sube el proyecto a tu repo y pega el enlace en la tabla del curso.

| Ticket | Puntos |
| --- | --- |
| 1 · Oferta relámpago | 6 |
| 2 · Hora de la estación | 5 |
| 3 · Prueba en consola | 4 |
| **Total** | **15** |
