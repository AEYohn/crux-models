# crux-models

Model files used by the CRUX climbing app's analysis server. Downloaded at build time with a pinned SHA-256.

## holds-int8mm-fp16w.onnx

Climbing-hold instance segmentation (Mask R-CNN R50), converted to ONNX (opset 16, dynamic input size), with int8 fully-connected layers and float16 weight storage.

- **Source:** [crux-climbing-hold-segmentation-models](https://github.com/d12/crux-climbing-hold-segmentation-models) by d12 (the "holds" model). An unrelated project that happens to share the name Crux.
- **Licence:** MIT, see [LICENSE-d12](LICENSE-d12). This conversion is distributed under the same licence.
- **Changes:** exported from the original Detectron2 weights with TracingAdapter; quantised with onnxruntime (dynamic int8 on MatMul/Gemm) and float16 weight storage. Same detection accuracy on our test set as the float32 export.
- **SHA-256:** `e61d3c1d0e6c3f96f935eaeba50183715a574db0a23f960d80782f4c9a0a5370`
