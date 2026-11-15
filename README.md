# Biblia Reina-Valera 1960 en JSON

La Biblia Reina-Valera 1960 completa en un solo archivo JSON: los **66 libros**, ordenados por libro, capítulo y versículo, y agrupados en Antiguo y Nuevo Testamento, con los títulos de sección.

Es el mismo texto que usa la app [Biblioteca Digital](https://github.com/Sherlock182/Biblioteca-Digital), revisado versículo por versículo contra el texto oficial actual.

| | Libros | Capítulos | Versículos |
|---|---:|---:|---:|
| Antiguo Testamento | 39 | 929 | 23 146 |
| Nuevo Testamento | 27 | 260 | 7 958 |
| **Total** | **66** | **1 189** | **31 104** |

## Archivos

| Archivo | Para qué sirve |
|---|---|
| [`biblia-rv1960.json`](biblia-rv1960.json) | Con sangría, fácil de leer y revisar (7.1 MB) |
| [`biblia-rv1960.min.json`](biblia-rv1960.min.json) | Compacto, para usar en apps y páginas web (5.0 MB) |

## Estructura

```json
{
  "titulo": "Biblia Reina-Valera 1960",
  "idioma": "es",
  "libros_total": 66,
  "capitulos_total": 1189,
  "versiculos_total": 31104,
  "libros": [
    {
      "numero": 1,
      "nombre": "Génesis",
      "clave": "Genesis",
      "testamento": "Antiguo Testamento",
      "grupo": "Pentateuco (La Ley)",
      "capitulos": [
        {
          "capitulo": 1,
          "versiculos": [
            {
              "versiculo": 1,
              "texto": "En el principio creó Dios los cielos y la tierra.",
              "titulos": [{ "tipo": "titulo", "texto": "La creación" }]
            }
          ]
        }
      ]
    }
  ]
}
```

Algunos versículos traen el campo **`titulos`**, que son los títulos que van antes del versículo. Cada uno tiene un `tipo`:

- `titulo`: el encabezado de una sección, como "La creación".
- `inscripcion`: la línea que va al inicio de un salmo, como "Salmo de David".
- `division`: una división mayor, como "Libro 1" en Salmos.

## Ejemplo de uso

```js
const biblia = require('./biblia-rv1960.json');

const juan = biblia.libros.find(l => l.nombre === 'Juan');
const versiculo = juan.capitulos[2].versiculos[15];
console.log(`Juan 3:${versiculo.versiculo} ${versiculo.texto}`);
```

```python
import json

with open('biblia-rv1960.json', encoding='utf-8') as f:
    biblia = json.load(f)

for libro in biblia['libros']:
    print(libro['numero'], libro['nombre'], len(libro['capitulos']), 'capítulos')
```

## Libros

**Antiguo Testamento (39):** Génesis, Éxodo, Levítico, Números, Deuteronomio, Josué, Jueces, Rut, 1 y 2 Samuel, 1 y 2 Reyes, 1 y 2 Crónicas, Esdras, Nehemías, Ester, Job, Salmos, Proverbios, Eclesiastés, Cantares, Isaías, Jeremías, Lamentaciones, Ezequiel, Daniel, Oseas, Joel, Amós, Abdías, Jonás, Miqueas, Nahúm, Habacuc, Sofonías, Hageo, Zacarías y Malaquías.

**Nuevo Testamento (27):** Mateo, Marcos, Lucas, Juan, Hechos, Romanos, 1 y 2 Corintios, Gálatas, Efesios, Filipenses, Colosenses, 1 y 2 Tesalonicenses, 1 y 2 Timoteo, Tito, Filemón, Hebreos, Santiago, 1 y 2 Pedro, 1, 2 y 3 Juan, Judas y Apocalipsis.

---

Desarrollado por **Ingeniero Oseas Nahun Montalvo Rogel** · [4603642023@mail.utec.edu.sv](mailto:4603642023@mail.utec.edu.sv) · [GitHub](https://github.com/Sherlock182)
