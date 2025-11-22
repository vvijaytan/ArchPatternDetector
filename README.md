# ArchPatternDetector
Automated Detection of Software Design Patterns &amp; Quality Attributes from UML/HLD/LLD Diagrams using CNN + GNN
[![Python](https://img.shields.io/badge/Python-3.11%2B-blue)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.4-orange)](https://pytorch.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-Demo-brightgreen)](http://localhost:8501)

**Automated Detection of Software Design Patterns & Quality Attributes from UML/HLD/LLD Diagrams using CNN + GNN**  
*Inspired by & Extending: "Automating Pattern Detection: Uncovering Software Architecture Design Patterns and its quality attributes through Image Analysis" (Vikash Kumar Vijaytan, M21AIE266, IIT Jodhpur, April 2025)*

Upload any diagram (even hand-drawn) → Detect patterns (e.g., Singleton: 92%) + Quality scores (e.g., Scalability: 0.88) + CBAM ROI suggestions!

![Demo GIF](https://via.placeholder.com/800x400?text=Upload+UML+%F0%9F%90%8D+Get+Patterns+%F0%9F%A7%A1)  <!-- Replace with your recorded GIF -->

## Features
- **Diagram Parsing**: YOLOv8 + OpenCV for boxes/arrows + EasyOCR for text
- **Graph Construction**: NetworkX → PyG for GNN input
- **Multi-Task Model**: GATv2 + CLIP for patterns (13 GoF) & qualities (5 attrs)
- **CBAM Integration**: Economic trade-off analysis
- **Dataset**: 5k+ synthetic UMLs via PlantUML + real-world (Kafka, Netflix)

## Quick Start
```bash
git clone https://github.com/vvijaytan/ArchPatternDetector.git
cd ArchPatternDetector
pip install -r requirements.txt

# Generate 5k synthetic diagrams
python notebooks/01_data_generation.py  # We'll create this next

# Run demo
streamlit run src/demo_app.py