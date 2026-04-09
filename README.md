# CEDEAR.ARB — Scanner de Arbitraje

Scanner en tiempo real de CEDEARs vs sus acciones en NYSE/NASDAQ. Detecta desabitrajes entre el precio local (BYMA) y el precio en el exterior (Yahoo Finance).

## Demo

Abrí `index.html` directamente en el browser, o subilo a GitHub Pages.

## Fuentes de datos

| Fuente | Datos | Delay |
|--------|-------|-------|
| Open BYMA Data | Precios ARS y USD (EXT) de CEDEARs | 20 min |
| Yahoo Finance | Precios NYSE / NASDAQ | 15 min |

## Funcionalidades

- **Scanner de mercado** — tabla completa con todos los CEDEARs NYSE/NASDAQ
- **Detección de arbitraje** — diferencia % entre precio BYMA (en USD) vs precio en NYSE
- **CCL implícito** — tipo de cambio calculado desde los propios precios de CEDEARs
- **Vista de detalle** — análisis completo por instrumento con señal de trading
- **Filtros** — por tipo de arbitraje (caro / barato / todos)
- **Ordenamiento** — por diferencia, precio, ticker

## Cómo usar

1. Abrí `index.html` en el browser
2. Presioná **"Escanear mercado"**
3. La app obtiene precios de BYMA + Yahoo Finance y calcula el desabitraje
4. Hacé click en cualquier CEDEAR para ver el detalle

## Nota técnica

El endpoint de Open BYMA Data tiene restricción CORS para llamadas directas desde el browser. La app usa la API de Anthropic como intermediario para obtener los datos. Si querés correrlo en modo standalone, pegá tu API key de Anthropic en el archivo `index.html` (variable `ANTHROPIC_API_KEY`).

## GitHub Pages

1. Subí el repo a GitHub
2. Ir a Settings → Pages → Source: `main` branch, carpeta `/root`
3. Tu app estará en `https://tuusuario.github.io/cedear-arb/`

## Estructura

```
cedear-arb/
└── index.html    # App completa (single file)
```

---

Desarrollado con Open BYMA Data + Yahoo Finance API
