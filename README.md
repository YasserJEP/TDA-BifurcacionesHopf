# TDA-BifurcacionesHopf
Detección de Bifurcaciones de Hopf mediante Topological Data Analysis (TDA)
Este repositorio explora la detección de bifurcaciones de Hopf en sistemas dinámicos mediante Análisis Topológico de Datos (TDA). Se implementan técnicas como homología persistente, complejos de Vietoris–Rips, embedding de Takens y diagramas de persistencia para identificar cambios topológicos en series temporales.

Sistemas dinámicos analizados
Hopf normal – Bifurcación de Hopf supercrítica (parámetro μ ∈ [-1, 1])

Lorenz – Sistema caótico clásico (parámetro ρ ∈ [20, 30])

Belousov–Zhabotinsky (BZ) – Reacción química oscilante (parámetro b ∈ [2, 5])

Metodología
Generación de series temporales – Integración numérica (RK4) de cada sistema

Embedding de Takens – Reconstrucción del espacio de fases (d=2, τ optimizado)

Homología persistente – Cálculo de diagramas de persistencia (H₀ y H₁)

Métricas topológicas – Norma L₁ de la curva de Betti-1 y máxima persistencia

Optimización de parámetros – Información mutua (τ) y FNN (m)

Estructura del repositorio
├── diagramas_persistencia/      # Subplots 3×3, 4×5 y 5×5
├── norma_L1/                    # Curvas de Betti-1 vs parámetro
├── maxima_persistencia/         # Máxima persistencia de H₁
├── exponentes_lyapunov/         # Exponente máximo λ₁ (referencia)
├── embedding_optimization/      # Información mutua y FNN
└── resultados/                  # Excel con datos y figuras PDF

Requisitos
pip install gtda ripser teaspoon numpy matplotlib scipy pandas scikit-learn

Resultados clave
Sistema	Parámetro crítico	Comportamiento topológico
Hopf normal	μ = 0	Aparición de H₁ (ciclo límite)
Lorenz	ρ ≈ 24.74	Transición al caos (máxima persistencia)
BZ	b ≈ 3.5	Bifurcación de Hopf


