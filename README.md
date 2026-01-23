# Clientes - Portal Eterea

Estructura para compartir documentos con clientes vía web.

## Estructura

```
/Clientes
  /oana
    index.html        ← Portal del cliente (lista de documentos)
    propuesta.html    ← Propuesta de entrenamiento
    factura-xxx.html  ← Facturas
    rutina-x.html     ← Rutinas de cada mesociclo
  /maria
    index.html
    ...
```

## Despliegue

```bash
cd Clientes
vercel --prod
```

## URLs resultantes

- `https://tu-proyecto.vercel.app/oana/` → Portal de Oana
- `https://tu-proyecto.vercel.app/oana/propuesta` → Su propuesta
- `https://tu-proyecto.vercel.app/maria/` → Portal de María

## Agregar nuevo cliente

1. Crear carpeta: `mkdir nombre-cliente`
2. Copiar index.html de otro cliente como plantilla
3. Personalizar contenido
4. `vercel --prod` para redesplegar
