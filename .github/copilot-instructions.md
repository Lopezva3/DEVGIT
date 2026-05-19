**Instrucciones para agentes AI — Proyecto SocOps (ES)**

Propósito
- Documento conciso para que agentes AI (Copilot/Chat agents) entiendan rápidamente cómo trabajar en este repositorio y realicen cambios útiles sin pedir información trivial.

Resumen rápido
- Proyecto: Aplicación Blazor WebAssembly de ejemplo llamada SocOps.
- Comandos principales:

```
dotnet run --project SocOps/SocOps.csproj
dotnet build SocOps/SocOps.csproj
```

- Ejecutar en desarrollo abre una SPA Blazor WebAssembly (ver [SocOps/wwwroot/index.html](SocOps/wwwroot/index.html)).

Dónde mirar primero
- [README.md](README.md): visión general del proyecto y enlaces principales.
- [SocOps/Program.cs](SocOps/Program.cs): punto de entrada y configuración de servicios.
- [SocOps/Components](SocOps/Components): UI principal (BingoBoard, GameScreen, StartScreen, etc.).
- [SocOps/Services](SocOps/Services): lógica de negocio (BingoGameService, BingoLogicService).
- [SocOps/Pages](SocOps/Pages): páginas Razor públicas (Home.razor, Counter.razor, Weather.razor).
- [SocOps/wwwroot](SocOps/wwwroot): assets estáticos y `index.html` usado por Blazor.
- `workshop/` y `docs/`: material didáctico y guías del taller; preferir enlazarlos en lugar de duplicar contenido.

Convenciones y recomendaciones para agentes
- Minimal por defecto: hacer cambios pequeños, bien probados y explicados en la descripción del PR.
- Linkear, no copiar: si la información ya existe en `docs/`, `workshop/`, o `README.md`, enlazarla en lugar de duplicarla.
- Estilo de commits: claro y conciso; preferir mensajes tipo "feature: ..." o "fix: ..." cuando aplique.
- No introducir dependencias nuevas sin justificar en la descripción del PR.

Qué automatizar o sugerir
- Tests: el repo no tiene una suite de tests definida; antes de agregar tests, proponer la estructura y las herramientas (xUnit/NUnit/MSTest).
- Formateo: seguir las reglas por defecto de `dotnet format` si se solicita formateo masivo.
- Documentación: cuando añadas o muevas componentes, actualizar `README.md` o `docs/` con enlaces relevantes.

Errores y señales de alerta comunes
- Cambios en `Program.cs` o `wwwroot/index.html` pueden afectar la inicialización de la SPA — ejecutar localmente.
- Evitar cambios globales a CSS sin revisar `SocOps/wwwroot/css/app.css` y `Layout/*.razor.css`.

Flujo recomendado para una modificación no trivial
1. Abrir un issue o describir el cambio en la PR. 2. Implementar cambios pequeños y atómicos. 3. Ejecutar `dotnet build` y probar localmente con `dotnet run`. 4. Actualizar `README.md` o `docs/` si aplica. 5. Crear PR con descripción y pasos para probar.

Comandos útiles

```
dotnet restore
dotnet build SocOps/SocOps.csproj
dotnet run --project SocOps/SocOps.csproj
```

Contacto y contexto adicional
- Contribuciones y normas: [CONTRIBUTING.md](CONTRIBUTING.md).
- Guía del taller y ejemplos prácticos: `workshop/`.

Siguientes personalizaciones útiles (sugeridas)
- Crear `AGENTS.md` para describir agentes especializados (frontend, tests, docs).
- Añadir skills/agents que ejecuten `dotnet build` y abran la SPA en un navegador de prueba.

Si necesitas más contexto, pregunta qué área del proyecto quieres modificar (UI, servicios, docs, tests).

**Lineamientos de Diseño**

- **Paleta y tokens:** Usar la paleta corporativa definida en `SocOps/wwwroot/css/app.css` (`--brand-primary`, `--brand-accent`, `--surface`, `--bg-soft`, `--text`). Evitar colores fuera de estos tokens salvo justificación.
- **Tipografía:** Preferir la pila `system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial` para coherencia; no introducir fuentes externas sin aprobación.
- **Espaciado y radios:** Usar variables y utilidades existentes (`p-`, `mb-`, `.container`, `--radius`) para mantener ritmo y consistencia; bordes suaves (8px) por defecto.
- **Componentes y superficies:** Componentes deben usar `.card`, `.btn`, y `--surface` para fondos; evitar estilos inline salvo casos puntuales y documentados.
- **Botones y CTAs:** Botones primarios con `--brand-primary`, secundarios transparentes con borde sutil; estados `:hover`, `:active` y `:focus` deben estar definidos y accesibles.
- **Accesibilidad:** Verificar contraste WCAG AA antes de aceptar cambios de color; elementos interactivos deben tener estados de foco visibles y `aria-` apropiados.
- **Responsive:** Diseñar para móviles primero; probar breakpoints básicos (320px, 768px, 1024px). BingoBoard y modales deben funcionar en pantallas pequeñas.
- **Assets y logos:** Añadir variantes en tonos de la paleta (p. ej. favicon azul/oscuro) en `SocOps/wwwroot/`; no subir imágenes excesivamente grandes.
- **Bootstrap / utilidades:** Sobrescribir selectivamente en `app.css`; evitar modificaciones directas a librerías de terceros.
- **Documentación de diseño:** Cuando añadas o cambies componentes visuales, incluye una breve nota en el PR describiendo los tokens usados, cambios de clases y capturas (si aplica).

Estos lineamientos buscan mantener coherencia visual, accesibilidad y facilidad de mantenimiento. Si quieres ampliar (ej.: tokens adicionales, guía de iconografía o ejemplos antes/después), lo agrego.
