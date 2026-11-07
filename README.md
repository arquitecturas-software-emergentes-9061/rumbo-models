# rumbo-models

Pesos de modelos que usa `rumbo-api/structural-mapper` para reconocer planos raster (PNG, JPEG, PDF escaneado).
Los archivos se publican como releases y el mapper los descarga solo, verificando su SHA-256; nadie necesita
instalar PyTorch ni exportar nada a mano.

## cubicasa5k-v1

| Archivo | Tamaño | SHA-256 |
|---|---|---|
| `cubicasa.onnx` | 66 MB | `ab630b6dc8540f77b594f0b75cb74506c1a2cdde0fa9ce2476423b2b84a994e4` |

- Origen: [CubiCasa5k](https://github.com/CubiCasa/CubiCasa5k), commit `c34440266665a11f4484eb06cd2e4b7d72ad76c1`,
  checkpoint oficial `model_best_val_loss_var.pkl` (SHA-256 `dd20b4e1bf1d670f2125107b079df06958b1ccd36e49a464ab739aeb00b8e7a2`).
- Exportado a ONNX con `structural-mapper/tools/export_cubicasa_onnx.py` (canales de muros, puertas, ventanas y
  ambientes; dimensiones espaciales dinámicas en múltiplos de 64; normalización RGB `[-1, 1]`).
- Se ejecuta con ONNX Runtime en CPU.

## Licencia

El modelo y los datos originales de CubiCasa5k están bajo **CC BY-NC 4.0**. Este repositorio los redistribuye
solo para el proyecto académico Rumbo (UPC, curso 1ASI0728), sin fines comerciales, con atribución a sus autores:

> Kalervo, A., Ylioinas, J., Häikiö, M., Karhu, A., & Kannala, J. (2019). CubiCasa5K: A Dataset and an Improved
> Multi-Task Model for Floorplan Image Analysis. SCIA 2019.
