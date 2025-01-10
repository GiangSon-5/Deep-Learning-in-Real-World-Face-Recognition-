# Deep-Learning-in-Real-World-Face-Recognition-

# I am using Kaggle's GPU for my project, and here is the link to my project (If you can't access it, it's because I set it to private mode): 
[Kaggle Notebook: Q4 Deep Learning in Real-World Face Recognition](https://www.kaggle.com/code/nguyenquyetgiangson/q4-deep-learning-in-real-world-face-recognition-a)

# Introduction: Deep Learning in Real-World Face Recognition Application

The project "Deep Learning in Real-World Face Recognition Application" aims to develop a practical face recognition system using the modern GhostFaceNet architecture (2023) and a dataset of 864 face images across 199 unique identities. The primary goal is to build a high-performance face recognition model capable of achieving over 98% accuracy, while also simulating user addition and login scenarios.

# DEMO
## Query image the user used for check-in:
![Query image the user used for check-in](https://raw.githack.com/GiangSon-5/Deep-Learning-in-Real-World-Face-Recognition-/main/images/Query%20image%20the%20user%20used%20for%20check-in.jpg)

## The system recognizes the query image matches the person with identity:
![The system recognizes the query image matches the person](https://raw.githack.com/GiangSon-5/Deep-Learning-in-Real-World-Face-Recognition-/main/images/The%20system%20recognizes%20the%20query%20image%20matches%20the%20person.jpg)
![The system recognizes the query image matches the person](https://raw.githack.com/GiangSon-5/Deep-Learning-in-Real-World-Face-Recognition-/main/images/The%20system%20recognizes%20the%20query%20image%20matches%20the%20person-2.jpg)

# 1. Steps Taken in the Project

## Face Recognition Model Development

*   **Model Architecture:** Utilized GhostFaceNet (2023), a highly efficient and lightweight architecture for face recognition tasks.
*   **Model Initialization:** Leveraged pre-trained weights from libraries such as TensorFlow Hub or PyTorch Hub.

## Normalization and Training

*   Generated embedding vectors for each face image using the model.
*   Applied L2 normalization to the vectors to enhance accuracy during comparisons.

## Simulating New Identity Addition

*   **Representative Vector Calculation:** Created a mean representative vector for each identity by averaging the embedding vectors of its images.
*   **Adding New Users:** Extended the dataset by adding new IDs and portrait images, updating the `data.csv` file to reflect the new user information.

## Simulating User Login

*   **Identity Recognition:** Used the embedding vector of the login image and computed its similarity with representative vectors in the dataset.
*   **Result:** Identified the user with the highest similarity score using cosine similarity.
*   **Verification:** Displayed all images from the dataset of the identified identity for visual confirmation.

# 2. Tools and Libraries Used

*   TensorFlow and Keras: For building and training the GhostFaceNet model.
*   FAISS (Facebook AI Similarity Search): Accelerated the search and similarity computation between embedding vectors.
*   OpenCV: For image preprocessing (resizing, color format conversion).
*   Scikit-learn: Used for L2 normalization and performance metrics calculation (ROC Curve, AUC).
*   Matplotlib: For visualizing model performance with ROC curves.
*   Pandas: For data processing and CSV file operations.

# 3. Performance and Results

*   **Accuracy:** Achieved a system accuracy of 99.5%, surpassing the initial goal of 98%.
*   **True Positive Rate (TPR):** Attained 98.8% at a low False Positive Rate (FPR).
*   **Search Speedup:** Integrated FAISS with the IndexFlatIP (Inner Product for Cosine Similarity) index, significantly reducing vector comparison time and enhancing image processing efficiency for larger datasets.
*   **Successful Simulation:** The system demonstrated high accuracy in adding new identities and recognizing them in login scenarios.

  ![Evaluation of model performance](https://raw.githack.com/GiangSon-5/Deep-Learning-in-Real-World-Face-Recognition-/main/images/Evaluation%20of%20model%20performance.jpg)

# 4. Model Evaluation and Improvements

## Advantages

*   GhostFaceNet reduced computational costs with its lightweight architecture, making it ideal for practical applications.
*   FAISS significantly sped up recognition in large datasets.
*   Embedding vectors were well-normalized, ensuring high accuracy during vector comparisons.

## Limitations

*   The relatively small dataset (864 images) might limit the model's scalability to larger and more diverse datasets.
*   Expanding the dataset is necessary to improve the model's generalizability.

## Future Enhancements

*   Integrate data augmentation techniques to improve dataset diversity.
*   Explore advanced architectures like ArcFace or SphereFace to enhance recognition performance further.

# 5. Explanation of Project Files

*   **`vn2db.npz`**: This file stores preprocessed data, including embedding vectors for each face, identities, and other essential information. It accelerates processing during face recognition or identity addition tasks.
*   **`GhostFaceNet_W1.3_S1_ArcFace.h5`**: This file contains the weights of the GhostFaceNet model after training. These weights are optimized for the face recognition task and integrate the ArcFace loss function, improving accuracy in distinguishing different identities.

# 6. YOLOv5 Integration in the Project

## Why Integrate YOLOv5

YOLOv5 was employed to detect faces in images before passing them to the GhostFaceNet model for recognition. This ensures the system can identify faces in multi-object images or real-time camera feeds.

## Integration Workflow

*   Used YOLOv5 to detect face locations in images or videos.
*   Cropped and normalized detected faces (resized to standard dimensions and converted color formats).
*   Fed the processed faces into the GhostFaceNet model for identity recognition.

## Achieved Benefits

*   Enhanced image processing capability in real-world scenarios, particularly when multiple objects are in the frame.
*   Optimized face detection and recognition speed by integrating YOLOv5 and FAISS.

# Summary

The project successfully developed a highly accurate face recognition system while flexibly simulating real-world scenarios like adding new identities and handling logins. Leveraging advanced tools such as TensorFlow, FAISS, GhostFaceNet, and YOLOv5 ensured high performance and reliability, paving the way for broad applications in security and identity management.


