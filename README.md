# ReLI: A Language-Agnostic Approach to Human-Robot Interaction
[![ReLI](https://img.shields.io/badge/ReLI%20-Website-lightblue?style=flat&logo=globe&logoColor=white)](https://sites.google.com/view/relimultlingual/overview)
[![ROS 1](https://img.shields.io/badge/ROS-Noetic-brightgreen.svg)](http://www.ros.org/)
[![ROS 2](https://img.shields.io/badge/ROS%202-Humble-blue.svg)](https://index.ros.org/doc/ros2/)
[![Python](https://img.shields.io/badge/Python-≥3.8-blue.svg)](https://www.python.org/)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![PyPI](https://img.shields.io/badge/PyPI-PIP-orange.svg)](https://pypi.org/)
[![GitHub Stars](https://img.shields.io/github/stars/LinusNEP/ReLI?style=social)](https://linusnep.github.io/ReLI/stargazers)
[![Last Commit](https://img.shields.io/github/last-commit/LinusNEP/ReLI.svg)](https://linusnep.github.io/ReLI/commits)

**ReLI** (Regardless of the Language of task Instructions) is a lingual-agnostic framework that enables autonomous agents to converse naturally, semantically reason about their environment, and perform downstream tasks, **regardless of the task instruction's modality or linguistic origin**.

## 🌟 Key Features

- **🌍 Language-Agnostic Interaction**: Supports 140+ languages, including high-resource, low-resource, and vulnerable languages
- **🎯 Multimodal Input**: Text and speech commands in any supported language
- **🤖 Real-World Robotic Affordances**: Grounds linguistic commands into executable robot actions
- **🧠 Advanced Perception**: Integrates CLIP, SAM, and MiDaS for robust visuo-lingual reasoning
- **⚡ High Performance**: Achieves >90% accuracy in multilingual instruction parsing and task execution
- **🔒 Safety-First**: User confirmation mechanism for critical actions

## 🎯 What ReLI Solves

Traditional human-robot interaction frameworks are constrained by:
- ❌ Language-specific training (primarily high-resource languages)
- ❌ Limited cross-lingual generalisation
- ❌ Inability to handle diverse linguistic backgrounds

ReLI breaks these barriers by:
- ✅ Exploiting cross-lingual capabilities of foundation models
- ✅ Supporting endangered languages, Creoles, and Vernaculars
- ✅ Enabling natural free-form conversation in any language

## 🚀 Getting Started
To reproduce the experiments and demos shown on the [project website](https://sites.google.com/view/relimultlingual/overview), we recommend following the installation instructions provided at [GETTING-STARTED.md](docs/GETTING-STARTED.md).

**Note: The codes will be made public soon after the peer review process is complete**

## 📝 Citation
If you use ReLI in your research, consider citing our paper:
```bibtex
@misc{nwankwo2025relilanguageagnosticapproachhumanrobot,
      title={ReLI: A Language-Agnostic Approach to Human-Robot Interaction}, 
      author={Linus Nwankwo and Bjoern Ellensohn and Ozan Özdenizci and Elmar Rueckert},
      year={2025},
      eprint={2505.01862},
      archivePrefix={arXiv},
      primaryClass={cs.RO},
      url={https://arxiv.org/abs/2505.01862}, 
}
```
## 🤝 Contributing
We welcome contributions! Please see our [Contributing Guidelines](https://...) for details.

### Development Setup
1.  Fork the repository
2.  Create a feature branch: `git checkout -b feature/amazing-feature`
3.  Commit changes: `git commit -m 'Add amazing feature'`
4.  Push to branch: `git push origin feature/amazing-feature`
5.  Open a Pull Request

## 📄 License
This work is licensed under a [Creative Commons Attribution International 4.0 License](https://creativecommons.org/licenses/by/4.0/).

## 🙏 Acknowledgments
This work was supported as part of the "MINEVIEW" project, funded by the Republic of Austria, Federal Ministry of Climate Action, Environment, Innovation and Technology.

**Repositories:**
- [TCC](https://github.com/LinusNEP/TCC-IRoNL)
- [ROMR](https://github.com/LinusNEP/ROMR.git)
- [Unitree_ros](https://github.com/macc-n/ros_unitree.git)

