# Image-captioning
Image captioning with Translation

## `caption_translate_speech` Function

The `caption_translate_speech` function performs three key tasks: generating a caption for an image, translating that caption into a specified language, and converting the translated caption into speech. Below is a detailed description of the function:

### Function Definition

```python
def caption_translate_speech(image_path, language='hin_Deva', speech_lang='hi'):
```

**Arguments:**
- `image_path`: The file path or URL of the image for which the caption is to be generated.
- `language`: The target language into which the caption will be translated. The default value is Hindi in Devanagari script (`hin_Deva`).
- `speech_lang`: The language for the text-to-speech output. The default value is Hindi (`hi`).

### Steps Performed by the Function

1. **Display Image:**
    ```python
    display(load_image(image_path))
    ```
    - This line loads and displays the image at the specified path or URL. The `load_image` function is used to handle both local files and URLs.

2. **Generate Caption:**
    ```python
    caption = get_caption(model, image_processor, tokenizer, image_path)
    print("Generated Caption:", caption)
    ```
    - The image is processed by a Vision Transformer (ViT) model to generate a descriptive caption. The caption is then printed.

3. **Translate Caption:**
    ```python
    translation = translate_text(caption, language)
    print("Translated Caption:", translation)
    ```
    - The generated caption is translated into the specified target language using the IndicTrans2 model. The translated caption is printed.

4. **Convert Text to Speech:**
    ```python
    return text_to_speech_colab(translation, lang=speech_lang)
    ```
    - The translated caption is converted into speech using the `gTTS` library. The function `text_to_speech_colab` generates and plays an audio file with the translated text in the selected speech language.

### Purpose

This function is designed to:
1. Load and display an image.
2. Generate a caption for the image using a pre-trained deep learning model.
3. Translate the generated caption into a specified Indian language.
4. Provide audio output of the translated caption, making it accessible to users with visual impairments.


 Image-Captioning/
├── app.py
├── reqirements.txt
├── Multilingual Image Captioning and Speech Synthesis.ipynb
├── static/
│   ├── uploads/
│   └── audio/
└── templates/
    └── index.html