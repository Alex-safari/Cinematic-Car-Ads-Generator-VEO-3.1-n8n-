# Cinematic-Car-Ads-Generator-VEO-3.1-n8n

**This template was created by Alex Safari.**
Subscribe to my YouTube channel for more AI automation tutorials:
👉 https://www.youtube.com/@alexsafari1

📺 **Watch the Full Tutorial Video:**
https://youtu.be/3rzR868er_M

## Overview
This workflow transforms a **single car photo** into a **multi-scene, cinematic car commercial**—automatically.

It uses an **AI Creative Director Agent** (Claude Sonnet 4.5) to write a professional storyboard, then generates and stitches multiple video clips using **VEO 3.1** and **Fal.ai FFMPEG**.

Perfect for agencies, marketers, or anyone wanting broadcast-quality video ads without a film crew or an editing suite.

## Workflow Breakdown

### 1. On Form Submission
* Collects the user-uploaded car photo.
* Captures the desired ad length (e.g., 24, 32, 40 seconds).
* Captures a simple creative description (or can be left vague).

### 2. Upload Car Photo
* Stores the uploaded photo in Cloudinary to get a public URL.

### 3. Get Number of Scenes
* Calculates how many 8-second scenes to create based on the total ad length selected.

### 4. Analyze Car Photo (Gemini 2.5 Pro)
* Performs detailed visual analysis of the car (model, color, materials, brand) and outputs a structured YAML.

### 5. Creative Director AI Agent (Claude Sonnet 4.5)
* Takes the car's YAML, scene count, and user's description.
* Writes a full, multi-scene storyboard in JSON format, complete with `CAM:`, `SVX:`, and `EMOTION:` tags for each 2-second beat.
* Uses a **"Smart Contextual Fallback"**: If the user description is vague, it auto-selects a theme (e.g., "Street to Track" for a sports car, "Conquering Nature" for an SUV).

### 6. Split Out Scenes
* Separates each scene from the AI-generated storyboard to be processed individually.

### 7. Call 'Kie.ai VEO 3.1' (Subworkflow)
* Generates an 8-second video clip for *each individual scene* using the original photo and the new scene prompt.

### 8. Aggregate Videos
* Collects the URLs of all generated video clips into a single array.

### 9. Call 'Fal.ai FFMPEG Merge' (Subworkflow)
* Stitches all the individual video clips together into one seamless, final video.

### 10. Download Video
* Downloads the final merged commercial.

## ⚙️ Tech Stack
* **n8n** – automation & workflow logic
* **VEO 3.1 (Kie.ai)** – image-to-video engine
* **Gemini 2.5 Pro (Google)** – image analysis
* **Claude Sonnet 4.5 (OpenRouter)** – creative direction agent
* **Fal.ai (FFMPEG)** – video merging
* **Cloudinary** – file management

---

📧 **Email me directly**: contact@loopsera.com
For quick questions, customisation requests, or workflow troubleshooting.

🌐 **Visit my website**: [https://loopsera.com](https://loopsera.com)
Explore more automation templates, services, and case studies.

📞 **Book a Discovery Call**: [https://cal.com/loopsera/ai-opportunity-audit](https://cal.com/loopsera/ai-opportunity-audit)
For businesses that need a custom AI agent built around their Instagram and ecommerce setup.

🎓 **1-on-1 Coaching Session**: [https://cal.com/loopsera/n8n-ai-agent-coaching-session](https://cal.com/loopsera/n8n-ai-agent-coaching-session)
Personalised coaching to help you build, troubleshoot, or optimise n8n AI workflows. Perfect for both beginners and advanced users.

💬 **Join the AI Builder’s Boardroom (Skool Community)**: [https://www.skool.com/ai-builders-boardroom-1717](https://www.skool.com/ai-builders-boardroom-1717) — a professional community for builders creating AI agents that talk, listen, and sell, focused on deploying the digital workforce of the future.
