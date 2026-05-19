🌐 [Português (BR)](README.pt_BR.md) | [Español](README.es.md)

# SocOps — Social Bingo para encuentros presenciales

SocOps es una pequeña SPA hecha en Blazor WebAssembly para jugar "Social Bingo" en eventos y rompehielos: comparte preguntas, encuentra personas que cumplan las condiciones y consigue 5 en línea.

🎮 Demo: **[Play the Game](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/)** • 📚 Guía: [workshop/ y docs](workshop/)

---

**Características principales**

- Juego interactivo en el navegador usando Blazor WebAssembly.
- Lógica de juego separada en `SocOps/Services` para facilitar pruebas y extensión.
- Contenido y guías didácticas en `workshop/` y `docs/`.

---

**Empezar (rápido)**

Prerequisitos:

- Instalado `.NET 10 SDK` o superior: https://dotnet.microsoft.com/download/dotnet/10.0

Desde la raíz del repositorio:

```bash
cd SocOps
dotnet run --project SocOps.csproj
```

La aplicación arranca como SPA y sirve la UI en `http://localhost:5000` (u otro puerto asignado).

Para compilar sin ejecutar:

```bash
cd SocOps
dotnet build
```

---

**Demo rediseñado**

Si has incorporado el nuevo rediseño y quieres probar el demo localmente o generar los artefactos estáticos para desplegar en GitHub Pages, sigue estas opciones:

- Ejecutar en modo desarrollo (rápido, con recarga):

```bash
cd SocOps
dotnet run --project SocOps.csproj
# Abrir http://localhost:5000 en el navegador
```

- Generar artefactos estáticos para despliegue (publicación):

```bash
cd SocOps
dotnet publish SocOps.csproj -c Release -o ./publish
# Los archivos listos para servir estarán en ./publish/wwwroot
```

- Servir la carpeta publicada localmente (opciones):

	- Con `dotnet-serve` (recomendado para .NET):

	```bash
	dotnet tool install --global dotnet-serve
	dotnet-serve -d publish/wwwroot -p 8080
	# Abrir http://localhost:8080
	```

	- Con `npx serve` (Node.js):

	```bash
	npx serve publish/wwwroot -p 8080
	```

- Despliegue en GitHub Pages:

	1. Publica los contenidos de `publish/wwwroot` en la rama `gh-pages` o en la carpeta que uses para GitHub Pages.
	2. Asegúrate de que el `base` en `index.html` (atributo `<base href="/">`) y las rutas a los recursos sean correctas para tu sitio.

Nota: el proceso de `dotnet publish` generará las referencias correctas a los archivos de Blazor con hash/fingerprint en la salida de `wwwroot`. Usa la carpeta publicada para evitar tener que editar manualmente `index.html`.


**Estructura útil**

- `SocOps/Program.cs`: punto de entrada y configuración de servicios.
- `SocOps/Components`: componentes UI principales (BingoBoard, GameScreen, StartScreen).
- `SocOps/Services`: lógica de juego (`BingoGameService`, `BingoLogicService`).
- `SocOps/wwwroot`: assets estáticos y `index.html`.
- `workshop/` y `docs/`: guías didácticas y material del taller.

---

**Contribuir**

1. Abre un issue para discutir cambios importantes.
2. Crea una rama descriptiva (`feature/...`, `fix/...`).
3. Haz commits claros y atómicos.
4. Envía un PR y referencia el issue.

Lee [`CONTRIBUTING.md`](CONTRIBUTING.md) para más detalles.

---

**Despliegue**

Este repositorio se despliega automáticamente en GitHub Pages al hacer push a la rama `main`.

---

**Licencia**

Este proyecto utiliza la licencia del repositorio: consulta el archivo `LICENSE`.

---

¿Necesitas que lo traduzca al inglés también o que añada capturas y badges? Abro a sugerencias.

