# GuitarLA

Tienda en línea de guitarras con carrito de compra, desarrollada con React, TypeScript y Vite.

**Demo:** https://guitarla-ts-erickgreco.netlify.app/

## Funcionalidades

- Catálogo de guitarras con imagen, descripción y precio.
- Agregar productos al carrito.
- Aumentar y disminuir la cantidad de cada producto.
- Eliminar productos o vaciar el carrito.
- Cálculo automático del total.
- Persistencia del carrito en `localStorage`.

## Stack

| Área                 | Tecnología        |
| -------------------- | ----------------- |
| UI                   | React             |
| Lenguaje             | TypeScript        |
| Bundler / Dev server | Vite              |
| Estilos              | CSS (`index.css`) |
| Despliegue           | Netlify           |
| Control de versiones | Git + GitHub      |

## Arquitectura

La lógica del carrito está separada de la interfaz: los componentes solo renderizan y la lógica de estado vive en un hook personalizado.

| Archivo                     | Responsabilidad                                                                     |
| --------------------------- | ----------------------------------------------------------------------------------- |
| `src/main.tsx`              | Punto de entrada; monta la aplicación en el DOM                                     |
| `src/App.tsx`               | Componente raíz; consume `useCart` y distribuye datos y funciones a los componentes |
| `src/components/Header.tsx` | Encabezado y vista del carrito                                                      |
| `src/components/Guitar.tsx` | Tarjeta de producto del catálogo                                                    |
| `src/hooks/useCart.ts`      | Hook personalizado con el estado y las operaciones del carrito                      |
| `src/data/db.ts`            | Catálogo de guitarras (datos locales)                                               |
| `src/types/index.ts`        | Tipos de TypeScript compartidos                                                     |
| `src/index.css`             | Estilos globales                                                                    |

## Ejecutar en local

Requisitos: Node.js (versión LTS) y npm.

```bash
git clone git@github.com:erickgreco/GuitarLA-TS.git
cd GuitarLA-TS
npm install
npm run dev
```

Scripts disponibles:

| Comando           | Descripción                                    |
| ----------------- | ---------------------------------------------- |
| `npm run dev`     | Servidor de desarrollo con recarga en caliente |
| `npm run build`   | Genera el build de producción en `dist/`       |
| `npm run preview` | Sirve localmente el build de producción        |

## Despliegue

El sitio se despliega en Netlify, conectado a este repositorio: cada `push` a `main` dispara un deploy automático.

| Configuración     | Valor           |
| ----------------- | --------------- |
| Build command     | `npm run build` |
| Publish directory | `dist`          |

## Autor

**Erick Gutierrez Sanchez**
GitHub: [@erickgreco](https://github.com/erickgreco)
