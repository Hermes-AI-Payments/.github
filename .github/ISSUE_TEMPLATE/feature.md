---
name: Feature
about: Cambio relevante para el producto que llega a un release. Si no cabe en una semana, cambia el tipo a Iniciativa y pártela en Features.
title: ""
type: Feature
projects: ["Hermes-AI-Payments/5"]
---

> **Cómo usar esta plantilla.** Cada sección trae una descripción, preguntas guía y un ejemplo. Reemplázalos por tu contenido; no deben quedar en el issue. Una sección que no aplica se borra completa.
>
> **Título:** verbo y resultado, en lenguaje de producto. Dice qué cambia, no qué se programa. Ejemplo: *Sostener 50 operaciones por segundo en el servicio de órdenes*. No: *Refactor del listener*.
>
> **En el tablero:** llena Producto (y Agente si es Agentes IA), Dimensión, Horizonte, Riesgo y Semana. Origen no lo llenas tú: se asigna al corte de la Y.
>
> **Sin datos de cliente ni de producción.** Ante la duda, el dato es sensible.

### Para qué

**Descripción:** qué capacidad o riesgo atiende y a qué objetivo del producto apoya: PoC, piloto u operación.

**Preguntas guía:**
- ¿Por qué existe? ¿Qué no puede hacer hoy el producto, el cliente o el equipo?
- ¿A qué objetivo del producto apoya?
- ¿Qué pasa si no se hace?

**Ejemplo:** el servicio de órdenes no tiene una cifra de rendimiento demostrada. Sin ella, el cliente no puede evaluar si el producto soporta su volumen. Es el primer escalón hacia las 100 operaciones por segundo que pide el objetivo.

### Resultado esperado

**Descripción:** qué se puede hacer o demostrar cuando esté verificada, que hoy no se puede.

**Preguntas guía:**
- ¿Qué cambia para producto o el cliente? Si nadie fuera de tecnología lo nota, probablemente es una Task.
- ¿Cómo se mide? ¿Qué cifra o evidencia lo demuestra?

**Ejemplo:** el servicio recibe 50 operaciones por segundo durante 30 minutos, sin rechazos ni acumulación de cola, y hay un reporte que lo demuestra.

### Criterios de aceptación

**Descripción:** las condiciones que se verifican al final, una por renglón, en forma Dado, cuando, entonces. Al menos una de producto, una de calidad y una de seguridad.

**Preguntas guía:**
- ¿Cada criterio se comprueba con un sí o un no?
- ¿Hay uno de producto, uno de calidad y uno de seguridad?
- ¿Alguien distinto del autor podría comprobarlos sin preguntarle nada?

**Ejemplo:**
- Dado el ambiente de pruebas con carga constante de 50 operaciones por segundo, cuando corre 30 minutos, entonces el 100 % de las operaciones se procesa sin error. *(producto)*
- Dada la misma carga, cuando termina la prueba, entonces el percentil 99 de latencia queda por debajo del umbral acordado con producto. *(calidad)*
- Dada la prueba de carga, cuando corre, entonces usa solo datos sintéticos y el reporte no expone llaves ni credenciales. *(seguridad)*

### Verificación

**Descripción:** el escenario de punta a punta que demuestra la Feature, el ambiente donde corre y quién la demuestra.

**Preguntas guía:**
- ¿Qué escenario de punta a punta la demuestra?
- ¿El ambiente es igual al del piloto o la PoC?
- ¿Quién distinto del autor la demuestra?

**Ejemplo:** la prueba de carga corre en un ambiente con la misma topología que el del piloto. La demuestra alguien distinto del autor, con el reporte y repitiendo la prueba.

### Dependencias

**Descripción:** lo que tiene que existir antes, dentro o fuera del equipo.

**Preguntas guía:**
- ¿Qué issues la bloquean? Enlázalos como *blocked by*.
- ¿Depende de algo externo: regulador, producto, cliente o proveedor? ¿Quién lo consigue y para cuándo?

**Ejemplo:**
- Blocked by: *Medir el rendimiento actual del servicio con una prueba de carga repetible*.
- Externa: ambiente de pruebas con la topología del piloto.

### Riesgos

**Descripción:** lo que puede impedir que se entregue o se verifique a tiempo.

**Preguntas guía:**
- ¿Qué puede salir mal?
- ¿Qué efecto tendría en el objetivo?

**Ejemplo:** si el cuello de botella está en un componente que no controlamos, como una base de datos administrada, la meta podría requerir un cambio de arquitectura que no cabe en la semana.

### Fuera de alcance

**Descripción:** lo que esta Feature no resuelve, aunque alguien podría esperarlo.

**Preguntas guía:**
- ¿Qué podría suponer producto o el cliente que viene incluido y no viene?

**Ejemplo:** rendimiento de salida. Ambientes distintos al del piloto.

### Por qué no entra

**Descripción:** solo si Horizonte es *No entra*; si entra, borra esta sección. La justificación técnica de por qué no se necesita para el objetivo del trimestre.

**Preguntas guía:**
- ¿Por qué no se necesita para el objetivo del trimestre?
- ¿Qué riesgo se acepta al no hacerla?
- ¿Cuándo debería revisarse?

**Ejemplo:** la prueba usa datos sintéticos, no datos reales del cliente. El cifrado en reposo que la nube aplica por defecto basta para esa etapa. Se acepta el riesgo de que un cliente pida llaves propias más adelante; se revisa al definir el alcance de producción.

### Referencia

**Descripción:** el expediente o documento en docs que atiende.

**Preguntas guía:**
- ¿Qué objetivo, capacidad o requerimiento del expediente cubre?

**Ejemplo:** objetivo del producto para el trimestre y expediente del producto en docs.

---

### Lista para Definido

Quien la escribe y quien la revisa, humano o IA, marcan esta lista. Pasa a Definido solo con todo marcado.

- [ ] El título dice qué cambia para el producto, no qué se programa.
- [ ] Cabe en una semana. Si no, el tipo cambió a Iniciativa y sus Features son sub-issues.
- [ ] El resultado esperado dice cómo se mide.
- [ ] Cada criterio de aceptación se comprueba con sí o no.
- [ ] Hay criterio de producto, de calidad y de seguridad.
- [ ] La verificación nombra el escenario, el ambiente y quién la demuestra.
- [ ] Las dependencias están enlazadas y las externas tienen responsable.
- [ ] Producto, Dimensión, Horizonte, Riesgo y Semana están llenos en el tablero.
- [ ] Cada dato tiene su fuente y no quedan pendientes abiertos marcados con doble llave y el nombre de quien los resuelve.
- [ ] No quedan descripciones, preguntas guía ni ejemplos de la plantilla.
- [ ] No contiene datos de cliente ni de producción.
