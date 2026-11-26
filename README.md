# render-carro-teste

Teste de velocidade: renderizar os quadros 1 a 12 da cena do carro
(`carro.blend`, 288 objetos, 720x1280, Cycles, 48 amostras, denoise)
em CPU no GitHub Actions (runner Linux 2 núcleos, sem GPU).

- `carro.blend.b64`: o arquivo Blender em base64 (o GitHub só aceita
  texto no envio; o workflow decodifica com `base64 -d`). MD5 do
  `.blend` original: `f27365e832a671ec0aa9c6d49a9f5ef5`.
- `.github/workflows/render-teste.yml`: baixa a imagem Docker
  `blendergrid/blender:5.3` (Blender 5.3.0, mesma versão do arquivo),
  renderiza os quadros 1–12, sobe os PNGs como artefato e publica
  os quadros + `render.log` na branch `output`.

NÃO é o render completo (2590 quadros) — só o teste de velocidade.
