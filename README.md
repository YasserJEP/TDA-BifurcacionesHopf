# Detección de Bifurcaciones de Hopf mediante Topological Data Analysis (TDA)

Este repositorio explora la detección de bifurcaciones de Hopf en sistemas dinámicos mediante **Análisis Topológico de Datos (TDA)**. Se implementan técnicas como homología persistente, complejos de Vietoris–Rips, embedding de Takens y diagramas de persistencia para identificar cambios topológicos en series temporales.

## Sistemas dinámicos analizados

| Sistema | Parámetro | Rango | Punto crítico |
|---------|-----------|-------|---------------|
| **Hopf normal** | μ | [-1, 1] | μ = 0 |
| **Lorenz** | ρ | [20, 30] | ρ ≈ 24.74 |
| **Belousov–Zhabotinsky (BZ)** | b | [2, 5] | b ≈ 3.5 |

## Metodología

1. **Generación de series temporales** – Integración numérica (RK4) de cada sistema
2. **Embedding de Takens** – Reconstrucción del espacio de fases (d optimizada, τ optimizado)
3. **Homología persistente** – Cálculo de diagramas de persistencia (H₀ y H₁)
4. **Métricas topológicas** – Norma L₁ de la curva de Betti-1 y máxima persistencia
5. **Optimización de parámetros** – Información mutua (τ) y FNN (m)

## Estructura del repositorio
├── diagramas_persistencia/
│ ├── hopf_normal_diagrams.py
│ ├── lorenz_diagrams.py
│ └── bz_diagrams.py
│
├── norma_L1/
│ ├── hopf_betti_norm.py
│ ├── lorenz_betti_norm.py
│ └── bz_betti_norm.py
│
├── maxima_persistencia/
│ ├── hopf_max_persistence.py
│ ├── lorenz_max_persistence.py
│ └── bz_max_persistence.py
│
├── exponentes_lyapunov/
│ ├── hopf_lyapunov.py
│ ├── lorenz_lyapunov.py
│ └── bz_lyapunov.py
│
├── embedding_optimization/
│ ├── hopf_embedding_opt.py
│ ├── lorenz_embedding_opt.py
│ └── bz_embedding_opt.py
│
└── resultados/
├── figures/
└── excel/
