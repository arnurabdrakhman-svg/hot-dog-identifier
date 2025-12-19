#  SeeFood: Hot Dog Identifier

##  Tutorial Overview
This project demonstrates how to deploy a computer vision model as a web application using **Gradio**. The app allows users to upload an image and uses a deep learning model to determine if the image contains a hot dog, recreating the famous "SeeFood" app from *Silicon Valley*.

## The Model: ResNet50
The application uses the **ResNet50** (Residual Network) architecture, a 50-layer deep Convolutional Neural Network. 



**Key Technical Details:**
* **Pre-training:** The model was pre-trained on the **ImageNet** dataset, which contains over 1.2 million images.
* **Logic:** While the model can identify 1,000 different objects, the app is programmed to specifically flag **Class Index 934** (Hot Dog).
* **Frameworks:** Built using **PyTorch** for model inference and **Gradio** for the UI.

##  How to Run
1. Open the `hot_dog_app.ipynb` in Google Colab.
2. Run all cells to generate a public `.gradio.live` link.

##  Future Improvements (Making the Team Happy)
To take this from a "Silicon Valley" prototype to a production-grade application that would satisfy a professional engineering team, I would implement the following:

1. **Dataset Expansion (MM-Food-100K):**
   Currently, the model uses ImageNet, which only has one "hotdog" category. Switching to the **MM-Food-100K** dataset would allow the model to distinguish between different types of hot dogs (e.g., corn dogs, chili dogs) and reduce "false positives" from similar-looking foods like carrots or sausages.
   
2. **Confidence Thresholding:**
   Instead of just picking the top result, I would implement a confidence threshold (e.g., 70%). If the AI is only 30% sure it's a hot dog, the app should say "I'm not sure," which builds user trust.

3. **Edge Deployment:**
   To make the team happy regarding costs and speed, I would convert the model to **ONNX** or **TensorRT** format to allow it to run directly on the user's phone (edge computing) rather than relying on a slow cloud server.
