# Detección de Bifurcaciones de Hopf mediante Topological Data Analysis (TDA)

Este repositorio explora la detección de bifurcaciones de Hopf en sistemas dinámicos mediante **Análisis Topológico de Datos (TDA)**. Se implementan técnicas como homología persistente, complejos de Vietoris–Rips, embedding de Takens y diagramas de persistencia para identificar cambios topológicos en series temporales.

## Sistemas dinámicos analizados

| Sistema | Parámetro | Rango | Punto crítico |
|---------|-----------|-------|---------------|
| **Hopf normal** | μ | [-1, 1] | μ = 0 |
| **Lorenz** | ρ | [20, 30] | ρ ≈ 24.74 |
| **Belousov–Zhabotinsky (BZ)** | b | [2, 5] | b ≈ 3.5 |

## Parámetros de embedding por sistema
| Sistema | τ (retardo) | m (dimensión) | Stride |
|---------|-------------|---------------|--------|
| Hopf normal | 26 | 2 | 2 |
| Lorenz | 16 | 2 | 2 |
| Belousov-Zhabotinsky | 57 | 2 | 5 |

## Parámetros por defecto de simulación
| Sistema | dt | T | SampleSize | Condiciones iniciales |
|---------|-----|-----|------------|----------------------|
| Hopf normal | 0.01 | 50-100 | 2000 | [0, 1.01] |
| Lorenz | 0.01 | 100 | 2000 | [6.74, 6.74, 22.74] |
| BZ | 0.01 | 80 | 4000 | [2, 5.01] |

## Scripts por categoría
| Categoría | Hopf normal | Lorenz | BZ |
|-----------|-------------|--------|-----|
| Diagramas de persistencia | `hopf_normal_diagrams.py` | `lorenz_diagrams.py` | `bz_diagrams.py` |
| Norma L₁ de Betti-1 | `hopf_betti_norm.py` | `lorenz_betti_norm.py` | `bz_betti_norm.py` |
| Máxima persistencia | `hopf_max_persistence.py` | `lorenz_max_persistence.py` | `bz_max_persistence.py` |
| Exponentes de Lyapunov | `hopf_lyapunov.py` | `lorenz_lyapunov.py` | `bz_lyapunov.py` |
| Optimización de embedding | `hopf_embedding_opt.py` | `lorenz_embedding_opt.py` | `bz_embedding_opt.py` |

## Dependencias del proyecto
| Librería | Versión | Uso |
|----------|---------|-----|
| `gtda` | ≥0.5.0 | Embedding de Takens, homología persistente |
| `ripser` | ≥0.6.0 | Diagramas de persistencia |
| `teaspoon` | ≥1.0.0 | Generación de sistemas dinámicos |
| `numpy` | ≥1.20.0 | Operaciones numéricas |
| `matplotlib` | ≥3.3.0 | Visualización |
| `scipy` | ≥1.7.0 | Integración de EDOs |
| `pandas` | ≥1.2.0 | Exportación de resultados |
| `scikit-learn` | ≥0.24.0 | FNN, NearestNeighbors |

## Metodología

1. **Generación de series temporales** – Integración numérica (RK4) de cada sistema
2. **Optimización de parámetros** – Información mutua (τ) y FNN (m)
3. **Embedding de Takens** – Reconstrucción del espacio de fases (d optimizada, τ optimizado)
4. **Homología persistente** – Cálculo de diagramas de persistencia (H₀ y H₁)
5. **Métricas topológicas** – Norma L₁ de la curva de Betti-1 y máxima persistencia

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

## Requisitos

```bash
pip install gtda ripser teaspoon numpy matplotlib scipy pandas scikit-learn
