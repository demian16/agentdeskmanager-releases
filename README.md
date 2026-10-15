# AgentDeskManager

App de escritorio para Windows que trabaja tus tareas con agentes de **Claude**:
1. Toma una tarea (de GitHub o escrita en la app).
2. Analiza tus repos y te propone un plan.
3. Implementa los cambios en una copia aparte y te muestra el diff.

**Nada se commitea, se sube ni se publica sin tu aprobación.** En las cuentas de trabajo podés dejarla en modo manual: la app no toca nada remoto y vos aplicás los cambios a tu copia.

## Descargar

**[Última versión →](https://github.com/demian16/agentdeskmanager-releases/releases/latest)**: bajá `AgentDeskManager-Setup-<versión>.exe` desde *Assets*.

Una vez instalada, la app se actualiza sola: busca versiones nuevas al abrirse y cada 4 horas, y te ofrece reiniciar. Después de cada actualización te muestra las novedades.

## Requisitos

- **Windows 10 u 11** (64 bits).
- **Git:** https://git-scm.com/download/win. Si no sabés si lo tenés, la app te avisa en el primer paso.
- **GitHub CLI**, solo si vas a usar tareas o repos de GitHub: https://cli.github.com.
- **Una cuenta de Claude:** un plan (Pro, Max, Team o Enterprise) o una API key de Anthropic. Claude Code ya viene incluido en la app; no hace falta instalarlo.

## Instalar

1. Ejecutá `AgentDeskManager-Setup-<versión>.exe`.
2. Windows puede mostrar **"Windows protegió su PC"**: el instalador no está firmado con un certificado comercial. Tocá **Más información → Ejecutar de todas formas**. Solo pasa la primera vez.
3. Elegí la carpeta (o dejá la que propone) e instalá. Se instala para tu usuario de Windows, sin permisos de administrador.

## Primeros pasos

Al abrirla por primera vez, la app arranca **vacía** (no toma ninguna cuenta de tu PC) y te guía en cuatro pasos:
1. **Requisitos:** revisa git y GitHub CLI.
2. **Cuenta de Claude:** iniciás sesión con tu plan en el navegador, o cargás una API key.
3. **De dónde salen tus tareas:** repos de tu PC (escribís las tareas en la app) o GitHub (iniciás sesión en el navegador, también con la cuenta de la empresa).
4. **Listo:** te explica cómo crear o abrir la primera tarea.

Después: abrí una tarea → **Analizar con Claude** → aprobá el plan → revisá el diff → commit y PR, o "Aplicar a mi copia local".

### Si es para el trabajo

- En **Cuentas → Permisos**, elegí **Manual y discreto**: la app solo lee las tareas. No commitea, no sube ni comenta, y lo que escribe el agente no menciona a la IA. Aplicás los cambios a tu copia y los commiteás vos.
- Si la empresa te da su propia cuenta de Claude, agregala en **Ajustes → Cuentas de Claude** y elegí qué cuenta usa cada etapa en **Ajustes → Modelos y cuentas por etapa**.
- Tené en cuenta que el código y las tareas se mandan a Claude (Anthropic) para analizarlos. Revisá que tu empresa lo permita.

## Tus datos

- Todo queda **en tu PC**, en `%APPDATA%\AgentDeskManager` (cuentas, tableros, historial), con un respaldo automático de la base en cada actualización.
- Los tokens y API keys se guardan en el **Administrador de credenciales de Windows**, nunca en archivos.
- La app no manda datos a ningún servidor propio: solo habla con GitHub, con Claude y con este repo para buscar actualizaciones.

## Algo no anda

- **Ajustes → Diagnóstico** revisa git, GitHub CLI, tu identidad de git, la cuenta de Claude y tus repos, y te dice qué hacer.
- **Ajustes → Limpieza** libera espacio de copias de trabajo viejas.
- **Ajustes → Datos → Restablecer la app** la deja como recién instalada. La base anterior queda en `backups`.
- Los registros del servidor están en `%APPDATA%\AgentDeskManager\logs\server.log`.

## Desinstalar

Desde **Configuración de Windows → Aplicaciones → AgentDeskManager → Desinstalar**. Tus datos en `%APPDATA%\AgentDeskManager` no se borran; si querés empezar de cero en otra instalación, borrá esa carpeta o usá "Restablecer la app" antes.
