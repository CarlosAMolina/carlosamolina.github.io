# GNU Linux

**Índice**

- [Network](network.md)
- [Reemplazar texto en archivos](#reemplazar-texto-en-archivos)

<a name="reemplazar-texto-en-archivos"></a>
## Reemplazar texto en archivos

```bash
grep -rlZe "EXAMPLETEXT==0\.5" --exclude-dir=.git . | xargs -0 sed -i 's/EXAMPLETEXT==0.5/EXAMPLETEXT==0.6/g'
```

