# GCP — Control de temas

Dashboard personal para llevar el control del estudio de Google Cloud, con meta: **GCP Cloud Support Engineer** (TELUS, tentativa feb–mar 2027).

- 16 bloques del temario integral (fundamentos, Linux, IAM, networking, compute, storage, bases de datos, containers, integración, observabilidad, seguridad, DevOps, fiabilidad, troubleshooting, laboratorios y entrevista).
- Cada tema tiene estado, descripción breve, fecha, resultado y enlace.
- **Estados:** Pendiente → En progreso → Dominado (solo con quiz + práctica/laboratorio completados).

## Ver en línea

Publicada con GitHub Pages: https://jonathanhdz-sv.github.io/gcp-dashboard/

## Cómo editar

La página es estática. Para actualizar el progreso, editar `index.html`:

1. **Estado de un tema:** cambiar la clase del `<div class="item ...">`:
   - `pend` → Pendiente (gris)
   - `prog` → En progreso (ámbar)
   - `dom` → Dominado (verde)
2. **Fecha, resultado y enlace:** editar los textos dentro de la línea `meta` de cada tema.
3. Los contadores y barras de progreso se calculan solos al abrir la página (no guardan datos).

Guías de sesión (ej. `sesion-vpc-movil.md`) se agregan a este repositorio y se enlazan desde los temas.
