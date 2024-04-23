# Image Background Changer

## Introduction
This program utilizes deep learning models to change the background of an input image based on user-defined masks and prompts. It incorporates Stable Diffusion Inpainting and the Segment Anything Model (SAM) for accurate inpainting and segmentation.


## Approach to the problem



### 1. Image Mask Generation
- Users select areas on the input image to create a mask using the Segment Anything Model (SAM).
- SAM predicts the background mask based on the input image and selected pixels.
- The mask is inverted to represent the background area to be changed.

Segment Anything Model is an open source model ,follow the link to learn more:-https://segment-anything.com/#:~:text=Segment%20Anything%20Model%20%28SAM%29%3A%20a%20new%20AI%20model,and%20images%2C%20without%20the%20need%20for%20additional%20training.

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

## Installation and setup
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

You can install the dependencies via pip(use pip install -r requirements.txt)

Install gradio using the source file provided in this link https://drive.google.com/file/d/1EiVYMDRgMssSgSpVVL4cguPDxaX1Tazq/view?usp=sharing 
which is a modified version of gradio to support image coordinate selection.

Download the tar.gz file and use pip install "gradio-4.27.0.tar.gz"

Also download the SAM weights from this link https://drive.google.com/file/d/1EeeI71RnBysV4BWDrQkJgJ0p9UYcHXJg/view?usp=drive_link

Follow this folder structure

- app.py
- weights/
  - sam_vit_h_4b8939.pth


## Usage
1. Run the program by executing the provided Python script (`app.py`).Use gradio app.py or python app.py to run the application
2. Upon launching the program, you'll see an interface with an input image, a mask image, and an output image display area.
3. Use the provided input image selection to choose an image whose background you want to change.
4. Define the mask by selecting areas of the image using the cursor. Each selection will be added to the mask.
5. Input a prompt text in the provided textbox.
6. Click the "Submit" button to initiate the background change process.
7. The program will generate an output image with the background changed according to the provided mask and prompt.

## Example
Here's a simple example to illustrate how to use the program:
- Input Image:
   - ![image](https://github.com/NivedKris/AI-DS-assignment/assets/100478612/a7d1a6b3-637e-46a0-bf51-135963fef848)

- Mask:
    - You can click on the object you want to mask(in this example it is the girl)
    - Click multiple times on different areas to make sure that the target object is fully masked.
    - ![image](https://github.com/NivedKris/AI-DS-assignment/assets/100478612/b229b894-3307-4d88-ab00-f4e3d95e13a5)
    - As you can see the object is masked

- Prompt:Im giving the prompt "Girl on a beach" and lets see the output
- Output Image:
    - Here is the output image for our prompt:-
    - ![image](https://github.com/NivedKris/AI-DS-assignment/assets/100478612/a0fadaf8-bb15-4ced-92ad-b764d8795513)
    - We can regenerate the background by pressing submit again
    - ![image](https://github.com/NivedKris/AI-DS-assignment/assets/100478612/ef384577-365b-4287-a35a-35c9884d0215)

-Entire Application:
    - ![image](https://github.com/NivedKris/AI-DS-assignment/assets/100478612/41f11177-82f1-40ef-984d-94a809084a9d)


The entire process takes around 9-10 seconds to complete based on the complexity of the prompt and object.



## Repository structure

-The input samples and their corresponding 5 output images with their prompts are given in this repository
-The repo structure is as follow:-
- README.md
- requirements.txt
- Application/
  - app.py
  - app.ipynb
- input_images/
  - product1.jpg
  - product2.jpg
  - product3.jpg
  - product4.jpg
  - product5.jpg
- output_images/
  - product1/
    - 1.jpg
    - 1.txt(prompt)
    - 2.jpg
    - 2.txt
    ......
  - product2/
  - product3/
  - product4/
  - product5/
    


## Notes
- Ensure that the provided input image is of sufficient quality and resolution for optimal results.
- Experiment with different prompts to achieve desired background changes.
- The program utilizes deep learning models, so running it on a machine with GPU support is recommended for faster processing.(Use t4 gpu if running in colab)

## Link for the live app

https://f833c190845167ea75.gradio.live

This is not a fully live server ,whenever you want to open it just send a request and the server will be turned on by me.(Didnt go for a fully live server due to high cost of running 24/7)


