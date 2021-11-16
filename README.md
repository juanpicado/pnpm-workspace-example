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
# Un solo directorio
pnpm test --filter ./packages/package1
# Todos los paquetes dentro de directorio packages (relativo)
pnpm test --filter {./packages}
```

o los paquetes que dependen de `@scope/package1`

```bash
pnpm test --filter ...^@scope/package1

# Tambien se puede usar directorio (dentro de ./packages) en combinacion con todos los paquetes dependientes de @scope/package 1 d
pnpm test --filter ...^{./packages}
```

o ejectuar multiples

```bash
pnpm test --filter "@scope/package1" --filter "@scope/package5"
```

Puedes excluir filtrar desde un commit

```bash
pnpm test --filter "...[origin/main]"
```

### Ejecutar Recursivo

Ejecutar `test` en todos los paquetes con `pnpm recursive`

```
  "scripts": {
    "test": "pnpm recursive test"
  },
```
