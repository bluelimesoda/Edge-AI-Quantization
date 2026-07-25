graph TD
    %% Base Model Stage
    subgraph Cloud / Server Environment [Cloud & Training Environment]
        A[Base LLM Weights <br> FP32 / High-Param] --> B[Knowledge Distillation]
    end

    %% Optimization Stage
    subgraph Quantization-Guided Optimization Pipeline [Optimization Frameworks: PyTorch / HF Optimum]
        B --> C[Structured Weight Pruning]
        C --> D[INT4 / INT8 Mixed-Precision<br>Quantization]
        D --> E[ONNX / Native Layer Optimization]
    end

    %% Edge Deployment Stage
    subgraph Target Hardware Execution [Edge Native Deployment]
        E --> F[Inference Runtime <br> ONNX Runtime Mobile / CoreML / TFLite]
        F --> G[Hardware-Accelerated <br> Layer Binding Pipeline]
        G --> H((Mobile NPU / GPU))
    end

    %% Performance Metrics
    H --> I[Result: Ultra-Low Latency & <br> >15 tokens/sec Throughput]
    H --> J[Result: 70%+ Memory Reduction <br> Zero OOM]

    %% Styling
    style Cloud / Server Environment fill:#f9f9f9,stroke:#333,stroke-width:2px
    style Quantization-Guided Optimization Pipeline fill:#e1f5fe,stroke:#0288d1,stroke-width:2px
    style Target Hardware Execution fill:#efebe9,stroke:#5d4037,stroke-width:2px
    style H fill:#ffe082,stroke:#ffb300,stroke-width:2px
