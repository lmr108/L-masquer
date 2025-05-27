# L-masquer

<div style="display: flex; align-items: center; gap: 10px; flex-wrap: wrap;">
  <!-- Built for badge -->
  <img src="https://img.shields.io/badge/Built%20for-Eiffage%20Energia%20y%20Sistemas-blue" alt="Built for Eiffage Energia y Sistemas" />
  <img src="https://img.shields.io/badge/Status-under%20development-orange" alt="Status: Under Development" />
  
  <!-- Confidentiality notice in a box -->
  <div style="border: 1px solid #ccc; padding: 6px 10px; border-radius: 4px; background-color: #f9f9f9;">
    <em>Sensitive code and data cannot be displayed due to company confidentiality.</em>
  </div>
</div>

<h4>Used Languages</h4>
<span> 
  <img src="https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54" />
</span>

<h4>Used Frameworks</h4>
<span>
  <img src="https://img.shields.io/badge/Keras-%23D00000.svg?style=for-the-badge&logo=Keras&logoColor=white" />
  <img src="https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white" />
</span>


## Description
A neural network developed with Keras that mimics the U-Net architecture but is much more efficient. Its goal is to segment photovoltaic panels to generate a binary mask of them, and—using the georeferencing of the points—to automatically create drone flight paths. 

## Data Collection
1. Georeferenced Layer Extraction
> Starting from a georeferenced panel layer, obtain the exact panel coordinates in the satellite imagery using web scraping.
>![imagen](https://github.com/user-attachments/assets/5bf82582-55de-462a-9f5c-0e4cf1d36e4e)
2. Gap Filling & Resolution Matching
> Process the panel layer to fill any gaps, then downsample the satellite image so that it matches the panel layer’s resolution.
> ![imagen](https://github.com/user-attachments/assets/c122ec58-deb1-4125-9c25-26ef868eea3f)
3. Patch Cropping
>Crop both the satellite image and its corresponding binary mask into 256 × 256 px patches, ensuring the mask is perfectly aligned with each real panel area.
<table>
  <tr>
    <td>
      <img src="https://github.com/user-attachments/assets/2e734787-fc45-48e3-8a8f-cb11aca96a33" alt="imagen 1" width="300" />
    </td>
    <td>
      <img src="https://github.com/user-attachments/assets/ce3b66f6-c5fc-4bac-b20f-c3ad6fe50178" alt="imagen 2" width="300" />
    </td>
  </tr>
</table>
4. Data Ready for the Network !!!  

## Performance 📈:
Tests
>🌱  Solar plants it has been trained on, but not with these specific images 🌱:
><img src="https://github.com/user-attachments/assets/0ee79235-7986-49e8-af7b-85bc2c55e3b0" alt="imagen 3" width="500" />
><img src="https://github.com/user-attachments/assets/4072e6fe-10f8-450f-a891-3dc2fca272bb" alt="imagen 4" width="500" />
><img src="https://github.com/user-attachments/assets/5ea503ff-8c57-4caa-b78c-8d14aa921c6c" alt="imagen 5" width="500" />
><img src="https://github.com/user-attachments/assets/29d4881f-5db8-411f-a02b-556caa26d823" alt="imagen 6" width="500" /> 

>>🌱 100% Solar plants never seen before 🌱:<br/>
>><img src="https://github.com/user-attachments/assets/495e7e2c-b056-4ead-8e32-65cf6324ad3b" alt="imagen 7" width="500" />
>><img src="https://github.com/user-attachments/assets/20750c41-7a72-41d5-9d1d-a420b232de64" alt="imagen 8" width="500" />
>><img src="https://github.com/user-attachments/assets/79289074-7938-469f-be00-60c1a156f7d5" alt="imagen 9" width="500" /> 
>><img src="https://github.com/user-attachments/assets/fa150667-5d7b-4ccd-9885-ba28f5bcacfc" alt="imagen 10" width="500" /> 

## Details
- **Development time:** 35 hours  
- **Images used:** 5,795  
- **Data augmentation:** No  

## Future work
1. **Implement data augmentation**  
   Introduce techniques (rotations, flips, brightness/contrast adjustments) to improve horizontal and diagonal panel detection.  

2. **Explore alternative Keras architectures**  
   Test different layer configurations and hyperparameters (e.g., deeper networks, attention blocks) to boost segmentation quality.  

3. **Evaluate transfer learning**  
   Leverage pretrained U-Net or other segmentation backbones if the custom model’s performance plateaus.  

4. **Final aim**  
   Perfect the model so that you can input a satellite image, automatically generate crops and predictions, then merge those predictions to produce a georeferenced panel mask—enabling panel mask extraction for any area   worldwide.
