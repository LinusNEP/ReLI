
## 🚀 Getting Started
We recommend following the setup instructions provided here to get started experimenting with ReLI.

### Prerequisites
- **ROS Noetic** (recommended) or ROS2 Humble & Jazzy (currently been implemented)
- **Python 3.8+**
- **PyTorch** with CUDA-capable GPU support (required for SAM, CLIP, MiDaS, and accelerated LLM usage)
- **OpenAI API key** or compatible LLM provider (DeepSeek, Claude, Gemini, llama.cpp, etc.)

### Installation (Native on host)
1.  For ROS 1, create a workspace and clone the repository:
   ```bash
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/src
catkin_init_workspace
git clone https://github.com/LinusNEP/SIL.git
cd ~/catkin_ws
```
2.  Create and activate a virtual environment:
   ```bash
python3 -m venv reli_env
source reli_env/bin/activate
```
3.  Install dependencies:
```bash
pip install -r src/ReLI/requirements.txt
```
4.  Build the ROS workspace:
```bash
cd ~/catkin_ws
catkin_make
source devel/setup.bash
```
5.  Configure API keys:
```bash
export OPENAI_API_KEY="your-api-key-here"
# Or configure in reli_config.yaml
```

### Docker Installation
1. Build the Docker image:
```bash
docker build -t reli_ros:gpu .
```
2. Run with GPU support:
```bash
docker run -it --rm \
    --gpus all \
    --env="DISPLAY=$DISPLAY" \
    --env="QT_X11_NO_MITSHM=1" \
    --volume="/tmp/.X11-unix:/tmp/.X11-unix:rw" \
    --network=host \
    reli_ros:gpu
```

## ⚙️ Configuration
**Core Configuration (`reli_config.yaml`)**
```yaml
# ReLI Core Settings
reli:
  enable_multilingual: true
  pre_execution_confirmation: true
  language_detection_auto: true
  max_action_sequence_length: 10
  enable_uncertainty_quantification: true

# LLM Configuration
llm:
  provider: "openai"  # openai, gemini, anthropic, llama.cpp
  model: "gpt-4o"
  max_tokens: 1000
  temperature: 0.1
  api_key: ""  # or via environment variable

# Vision-Language Models
vision:
  clip_model: "ViT-B/32"
  sam_checkpoint: "models/sam_vit_h_4b8939.pth"
  midas_model: "DPT_Large"
  detection_confidence_threshold: 0.7

# Multilingual Settings
multilingual:
  fallback_language: "en"
  enable_transliteration: true

# ROS Topics
topics:
  # Input/Output
  command_input: "/reli_command"
  response_output: "/reli_response"
  action_plan: "/reli_action_plan"
  user_confirmation: "/reli_confirmation"
  
  # Perception
  camera_color: "/camera/color/image_raw"
  camera_depth: "/camera/depth/image_rect_raw"
  pointcloud: "/camera/depth/points"
  
  # Control
  cmd_vel: "/cmd_vel"
  odom: "/odom"
  navigation_goal: "/move_base_simple/goal"
```

### Running ReLI
1.  Launch ReLI core:
```bash
cd ~/catkin_ws
source devel/setup.bash
roslaunch reli_ros reli_ros.launch
```
2.  Start the chat interface:
```bash
source devel/setup.bash
roslaunch reli_ros reli_chatGUI.launch
```
3. Interact naturally in any supported language:
   - **Text:** Type commands in your preferred language
   - **Speech:** Use microphone for voice commands

### Customising Destinations
Define robot-relevant spaces (rooms, locations, zones) in `reli_config.yaml`:
```yaml
destinations:
  living_room:
    display_name: "Living Room"
    aliases: ["lounge", "sitting area"]
    coords: {x: 1.0, y: 2.5, z: 0.0}
```
Destinations are automatically interpreted by the Action Executor and used for navigation planning.


