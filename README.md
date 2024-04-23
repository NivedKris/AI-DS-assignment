# Image Background Changer

## Introduction
This program utilizes deep learning models to change the background of an input image based on user-defined masks and prompts. It incorporates Stable Diffusion Inpainting and the Segment Anything Model (SAM) for accurate inpainting and segmentation.


## How it Works?



### 1. Image Mask Generation
- Users select areas on the input image to create a mask using the Segment Anything Model (SAM).
- SAM predicts the background mask based on the input image and selected pixels.
- The mask is inverted to represent the background area to be changed.

### 2. Inpainting Process
- The input image and generated mask are resized to a fixed size (512x512) to match the model's input requirements.
- The Stable Diffusion Inpainting Pipeline is applied to the input image to change the background.
- The pipeline utilizes deep learning techniques to inpaint the background based on the provided prompt and mask.

### 3. Output
- The resulting image with the changed background is displayed as the output.

### 4. User Interaction
- Users interact with the system by selecting areas on the input image, inputting prompts, and triggering the background change process.
- They can experiment with different masks and prompts to achieve desired background changes.

This solution involves utilizing deep learning models (SAM and Stable Diffusion Inpainting) for image segmentation and background inpainting, enabling users to change backgrounds interactively based on their inputs and preferences.

## Installation
To run the program, you need the following dependencies:

- Python 3.11
- gradio
- numpy
- torch
- diffusers
- PIL
- openCV-python
- torchvision
- matplotlib
- etc......

You can install the dependencies via pip(use the requirements.txt)


## Usage
1. Run the program by executing the provided Python script (`image_background_changer.py`).
2. Upon launching the program, you'll see an interface with an input image, a mask image, and an output image display area.
3. Use the provided input image selection to choose an image whose background you want to change.
4. Define the mask by selecting areas of the image using the cursor. Each selection will be added to the mask.
5. Input a prompt text in the provided textbox.
6. Click the "Submit" button to initiate the background change process.
7. The program will generate an output image with the background changed according to the provided mask and prompt.

## Example
Here's a simple example to illustrate how to use the program:
- Input Image: [Provide an example input image]
- Mask: [Describe the mask selection process]
- Prompt: [Provide an example prompt text]
- Output Image: [Provide the resulting output image]

## Notes
- Ensure that the provided input image is of sufficient quality and resolution for optimal results.
- Experiment with different prompts to achieve desired background changes.
- The program utilizes deep learning models, so running it on a machine with GPU support is recommended for faster processing.

---

Feel free to customize this README according to your preferences and specific requirements!
