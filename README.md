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

## Details
- **Development time:** 40 hours  
- **Hardware:** Intel Core i9-10900X
- **Frameworks & versiones:** CUDA: 11.8 | cuDNN: 8.7 | torch: 2.6.0+cu118 | Python: 3.12.10
- **Training time:** ~2.30h
  
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

><img src="https://github.com/user-attachments/assets/a1ec313b-6544-4d4c-b673-0f466623c234" alt="imagen 3" width="500" />
><img src="https://github.com/user-attachments/assets/12725775-29b3-4beb-b53b-46cbb4eda8f3" alt="imagen 4" width="500" />
><img src="https://github.com/user-attachments/assets/8e907192-9ae3-4220-815d-62d0bbbc3a0e" alt="imagen 5" width="500" />
><img src="https://github.com/user-attachments/assets/98f2c5a4-9434-470b-9e3d-20a52c9821ee" alt="imagen 6" width="500" /> 
><img src="https://github.com/user-attachments/assets/a5a10e74-5220-4cdd-9773-b83fd2dad208" alt="imagen 12" width="500" /> 

>>🌱 100% Solar plants never seen before 🌱:<br/>
>><img src="https://github.com/user-attachments/assets/7b7956a9-e4a4-451c-aef3-9e4a5df648ac" alt="imagen 7" width="500" />
>><img src="https://github.com/user-attachments/assets/20750c41-7a72-41d5-9d1d-a420b232de64" alt="imagen 8" width="500" />
>><img src="https://github.com/user-attachments/assets/e91aefa6-1df3-4a18-a99b-960ebb249198" alt="imagen 9" width="500" /> 
>><img src="https://github.com/user-attachments/assets/d9dfb6f2-1b97-4cce-9369-60c7e765f298" alt="imagen 10" width="500" />
>><img src="https://github.com/user-attachments/assets/867d481d-b2f3-4064-a873-9d94841f35bf" alt="imagen 11" width="500" /> 
>><img src="https://github.com/user-attachments/assets/c83cee33-51b8-412c-92ee-97b035359158" alt="imagen 13" width="500" />
>>
## Future work
1. **Implement data augmentation**  
   Introduce techniques (rotations, flips, brightness/contrast adjustments) to improve horizontal and diagonal panel detection.  

2. **Explore alternative Keras architectures**  
   Test different layer configurations and hyperparameters (e.g., deeper networks, attention blocks) to boost segmentation quality.  

3. **Evaluate transfer learning**  
   Leverage pretrained U-Net or other segmentation backbones if the custom model’s performance plateaus.  

4. **Final aim**  
   Perfect the model so that you can input a satellite image, automatically generate crops and predictions, then merge those predictions to produce a georeferenced panel mask—enabling panel mask extraction for any area   worldwide:
   
   ![imagen](https://github.com/user-attachments/assets/66d8cdb3-6a1e-40bb-9a5c-5dce5ed41bd1)

## Model
![42b03f7b-4f20-45f2-8258-4dd7f3ee8e22-1](https://github.com/user-attachments/assets/5647f841-ca18-48f8-acda-41d1ce58f0ff)

![L_masker](https://github.com/user-attachments/assets/1b891b6e-1b9a-48bb-a52e-74edfa6d46f2)


