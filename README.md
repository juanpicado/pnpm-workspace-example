# pnpm-workspace-example

### Haciendo referencia a otros paquetes del repositorio

Cualquier version `*` (no recomendable)

```bash
  "dependencies": {
    "@scope/package1": "workspace:*"
  },
```

version specifica

```bash
  "dependencies": {
    "@scope/package1": "workspace:1.0.0"
  },
```

### Filtrando paquetes

Ejecutando todos los paquetes del workspaces del scope `@scope`

```bash
pnpm test --filter "@scope/\*"
```

o un solo paquete

Ejecutando todos los paquetes del workspaces del scope `@scope`

```bash
pnpm test --filter "@scope/package1"
```

o directorio

```bash
pnpm test --filter ./packages/package1
pnpm test --filter {package1}
```

o los paquetes que dependen de `@scope/package1`

```bash
pnpm test --filter ...^@scope/package1
```

### Ejecutar Recursivo

Ejecutar `test` en todos los paquetes con `pnpm recursive`

```
  "scripts": {
    "test": "pnpm recursive test"
  },
```
