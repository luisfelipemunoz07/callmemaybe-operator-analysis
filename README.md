# 📞 CallMeMaybe — Análisis de Eficiencia de Operadores

> Identificación de operadores ineficientes en un servicio de telefonía virtual usando clustering no supervisado y pruebas de hipótesis estadísticas.

---

## 🎯 Problema

Una empresa de telefonía virtual necesitaba dar a sus supervisores una herramienta para detectar qué operadores estaban rindiendo por debajo del estándar. El reto: no había una definición clara de "ineficiente", y los datos tenían ruido considerable que distorsionaba cualquier comparación directa.

---

## 🔍 ¿Qué hice?

**1. Limpieza y Exploración de Datos (EDA)**
Trabajé con dos datasets: registros de llamadas por operador y datos de clientes. Detecté valores atípicos extremos usando el método IQR, estableciendo un umbral de 54 llamadas diarias para garantizar comparaciones justas entre operadores.

**2. Segmentación con K-Means Clustering**
En lugar de ordenar operadores arbitrariamente, usé clustering no supervisado para dejar que los datos definieran los grupos naturales de comportamiento. Determiné el número óptimo de clusters (4) mediante análisis de dendrograma jerárquico.

**3. Validación Estadística**
Apliqué pruebas Mann-Whitney U con corrección de Bonferroni para confirmar que las diferencias entre el grupo ineficiente y el resto eran estadísticamente significativas y no producto del azar.

---

## 📊 Resultados

| Métrica | Grupo ineficiente | Resto de operadores |
|---|---|---|
| Tiempo de espera promedio | 3,210 seg. | 658 – 900 seg. |
| Llamadas salientes promedio | 185 | 380 – 620 |
| Llamadas perdidas promedio | 4.5 | 2.8 – 5.1 |

- **6 operadores identificados** como ineficientes de un total de 945 (0.6%)
- Diferencias confirmadas estadísticamente en 2 de 3 métricas (p < 0.0167)
- Entregable final: presentación ejecutiva para audiencia no técnica

---

## 🛠️ Stack técnico

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=flat&logo=scipy&logoColor=white)

| Librería | Uso |
|---|---|
| `pandas` / `NumPy` | Limpieza y transformación de datos |
| `scikit-learn` | K-Means Clustering, StandardScaler |
| `SciPy` | Mann-Whitney U, clustering jerárquico |
| `Matplotlib` / `Seaborn` | Visualización exploratoria |

---

## 📁 Estructura del repositorio

```
📁 callmemaybe-operator-analysis/
│
├── 📓 notebook (1).ipynb
├── 📄 CallMeMaybe_Analisis_Operadores.pdf
├── 📄 README.md
└── 📁 data/
    ├── 📄 README.md
    ├── 📄 telecom_dataset_us.csv
    └── 📄 telecom_clients_us.csv
```
---

## 💡 Lo que aprendí

1. **La limpieza de datos es el análisis.** Detectar outliers no fue un paso previo — fue una decisión metodológica que cambió todo el modelo.
2. **Clustering sin validación estadística es solo una historia.** Necesitas las pruebas de hipótesis para decir con confianza que los grupos son reales.
3. **Un p-value no le dice nada a un supervisor.** Aprendí a traducir resultados estadísticos en lenguaje de negocio accionable.

---

## 📬 Contacto

**Luis Felipe Muñoz**  
[LinkedIn](https://www.linkedin.com/in/luismunozmartinez/) · [GitHub](https://github.com/luisfelipemunoz07)    
