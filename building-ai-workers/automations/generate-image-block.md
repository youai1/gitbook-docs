---
description: Use AI models to generate images in your AI Workers.
---

# Generate Image Block

The **Generate Image Block** sends a text prompt to an AI model and returns an image URL based on the description provided.

## **Configurations**

### **Prompt**

Define the text description of the image you want the AI model to generate. Use `{{variables}}` to make the prompt dynamic based on a previous step in the workflow.

[Learn about variables →](../variables.md)

### **Output Variable**

Creates a new variable and saves the image URL to it. Enter a `variable_name` \*\*\*\*to store the response for later use in the workflow.

### **Model Settings**

Choose from MindStudio’s library of image-generation models, optimized for various styles and quality levels.

Each AI image model may have unique configuration options for fine-tuning outputs, such as additional style parameters, rendering quality, negative prompt or advanced filters. make sure you review the specific settings for each model you select.

***

## Writing Image Prompts

Crafting effective prompts for image generation ensures that the AI model produces visuals that align with your expectations. A good prompt provides clarity, context, and enough detail to guide the model’s output without being overly restrictive.

### **Tips for Writing Effective Prompts**

* **Be Clear and Specific:** Use precise language to describe the desired image. Focus on key visual elements, such as objects, environments, colors, and textures.
* **Add Context and Atmosphere:** Describe the mood, setting, or story behind the image to provide creative direction.
* **Include Style and Aesthetic Details:** Specify the art style or medium (e.g., photorealistic, watercolor, comic-style, abstract). Mention influences like "minimalist," "vintage," or "cinematic glow."
* **Use Action and Interaction:** Incorporate actions or interactions to make the image dynamic.
* **Provide a Color Palette:** Specify dominant colors to guide the tone of the image.
* **Specify Composition and Layout:** Include details about positioning, perspective, and framing.
* **Add Creative Flourishes:** Suggest unique or imaginative elements to include in the image.

### **Common Pitfalls to Avoid**

* **Being Too Vague**: "Create an image of a tree." → Lacks detail and context.
* **Overloading the Prompt**: Avoid including too many unrelated elements, which can confuse the model.
* **Leaving Out Key Details**: Forgetting to mention the desired style, mood, or setting can lead to generic results.

### **Example Image Prompt**:

{% code overflow="wrap" %}
```markdown
Generate a hyper-realistic image of a futuristic cityscape at sunset. The city should feature towering skyscrapers with glass facades reflecting the orange and pink hues of the sunset. 

Include floating vehicles with soft neon underlights flying between the buildings, creating a sense of motion. 

In the foreground, add a bustling street market with humans and humanoid robots interacting, showcasing a blend of futuristic technology and traditional market stalls. 

Use a warm color palette dominated by orange, pink, and gold, with subtle accents of teal and blue in the neon lights. 

The sky should be filled with soft clouds, and the setting sun should cast long shadows across the scene. 

Ensure the image feels dynamic and alive, capturing both the grandeur of the skyline and the vibrancy of the street-level activity. The overall style should balance photorealism with a slight cinematic glow for a futuristic yet inviting atmosphere.
```
{% endcode %}

#### Example Output (DALL-E 3):

![DALL·E Output: A hyper-realistic futuristic cityscape at sunset, featuring towering skyscrapers with glass facades reflecting orange and pink hues. Floating vehicles](<../../.gitbook/assets/DALL·E 2024-11-22 14.28.14 - A hyper-realistic futuristic cityscape at sunset, featuring towering skyscrapers with glass facades reflecting orange and pink hues. Floating vehicles.webp>)