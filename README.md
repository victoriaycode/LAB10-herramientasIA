# 🚀 AI-Driven Development (BPIR Standard)

[cite_start]Este repositorio centraliza el flujo de trabajo y los artefactos de ingeniería para el desarrollo de software asistido por Inteligencia Artificial, siguiendo el estándar **BPIR** (Brief, Plan, Implement, Review)[cite: 1, 38].

## 🛠️ Metodología BPIR
[cite_start]Para maximizar la calidad del código y mitigar las alucinaciones de la IA, seguimos este ciclo riguroso[cite: 1, 2]:

1.  [cite_start]**B**rief: Definición técnica estricta y arquitectura vertical antes de codificar[cite: 1, 27].
2.  [cite_start]**P**lan: División del proyecto en hitos (Checkpoints) con un protocolo de commits atómicos[cite: 29, 45].
3.  [cite_start]**I**mplement: Generación de código respetando la separación de responsabilidades (Domain → Infra → UI)[cite: 27, 30].
4.  [cite_start]**R**eview: Auditoría obligatoria de 5 puntos críticos antes de integrar cualquier cambio[cite: 1, 38].

## 📂 Estructura del Proyecto
```text
herramientas-ia/
├── 01-planning/
│   ├── plantilla-brief-ia.md    # Estándar para nuevos módulos 
│   └── protocolo-review-ia.md   # Checklist de seguridad y calidad 
└── [módulos-del-proyecto]/      # Código organizado por capas [cite: 27, 30]
