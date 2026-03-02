# AI-Home-Butler

  以AI为核心部署在私人NAS或个人电脑上的智能家居系统，超越如小米.华为的“人工智障”， 整合现有家居平台（Home Assistant）和AI角色扮演系统（Silly Tavern），定制专属于自己的家庭管家，本地部署避免隐私泄露

# 私人想法
-把我心中的白月光做成ai陪伴在我的生活之中

##  核心亮点

- 100%本地隐私（Ollama + SillyTavern 全离线）
- 已深度集成酒馆系统（SillyTavern）
- Home Assistant 深度联动——实装未联动
- Live2D具象化形象 + 嘴型同步 + 情绪表情——未实装
- 语音输入交互——未实装
- 小车（含摄像头.音响）类似moss的实体机器人作为AI载体（非运算服务器）——未实装

##   开发路线与当前进度
- [x] 第一阶段：大脑与灵魂（Ollama + SillyTavern + 记忆库）
- [x] 第二阶段：感知与控制（HA + Frigate + 语音）
- [ ] 第三阶段：Live2D具象化形象 + 嘴型同步
- [ ] 第四阶段：混合大脑（云端API增强）
- [ ] 第五阶段：实体化与自动化（会走路的小车）

##  运行逻辑

-将AI女友/男友与智能家居相结合，实现独居个体的人文关怀，弥补市面上各大厂的智能家居系统没有人味且智商堪忧的缺点与不足，甚至可拓展为帮助孤寡老人的家居系统，检测老人状态在意外情况下及时联系外界，给与老人情绪价值。或许可以根据老人因意外离去的孩子的性格特点制作AI使老人留存念想（可能违背人道主义仅作为未来展望）

##  技术栈（友好、免费）
- **本地LLM运行**：Ollama或LM Studio + OpenWebUI前端
- **智能家居**：Home Assistant
- **集成方式**：
  - HA的Conversation Agent集成Ollama（官方已支持）
  - 或用HA的REST API/Webhook触发自定义Python脚本调用（SillyTavern）
- **语音交互**（可选加分）：
  - Wyatt（开源语音助手）+ HA集成

##  潜在问题与规避
- 性能：NAS上跑大模型可能卡，建议默认用7B模型，提供“进阶模式”切换更大模型。对硬件要求较高（或许你可以试试网上很火的mac mini）如果你不介意隐私方面的问题可以使用各大厂商的api接入本系统提高ai智能
- 主动性太强会烦人，对这个主动性的平衡不好处理，我个人实验来说仍仅仅是我提出要求它来解决的情况，未达成目标
- 女友形式争议：这种类人的设计可能引发伦理问题的争议，我设计了健康提醒“AI设定中明确自己的身份是AI”
-AI对智能家居的控制权限造成的安全隐患：在AI设定中加入安全协议，在用户使用设定的安全词后强行执行指令

## Demo
![聊天界面](images/chat-demo.png)
![AllTalk代码界面](images/AllTalk-demo.png)
![HA联动面板](images/ha-panel.png)

Star History
![Star History Chart](https://api.star-history.com/svg?repos=weyand138-netizen/AI-Home-Butler&type=Date)

#  贡献
-欢迎各位在此想法上自由创作或者与我讨论想法
Email: weyand138@gmail.com

#许可证MIT License —— 随便用、随便改、随便商用

#本项目引用的开源项目:
Ollama:https://ollama.com/
Silly Tavern:https://github.com/SillyTavern/SillyTavern
Home Assistant:https://www.home-assistant.io/
OpenWebUI:https://github.com/open-webui/open-webui
AllTalk TTS:https://github.com/AllTalkTTS/AllTalkTTS

##  快速启动

```bash
git clone https://github.com/weyand138-netizen/AI-Home-Butler.git
cd AI-Home-Butler
docker compose up -d

## 手动部署
- curl -fsSL https://ollama.com/install.sh | sh
  ollama pull llama3.2  
- git clone https://github.com/SillyTavern/SillyTavern.git
  cd SillyTavern
  npm install
  npm start
- 部署成功后打开浏览器进入系统配置（详情参考Ollama    SillyTavern   AllTalk TTS   HS的部署步骤）
1.在SillyTavern左上角点击API  
2.选择 Ollama  
3.URL填：http://localhost:11434  
4.测试连接成功即可


