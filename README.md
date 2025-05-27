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
![imagen](https://github.com/user-attachments/assets/2e734787-fc45-48e3-8a8f-cb11aca96a33)
![imagen](https://github.com/user-attachments/assets/ce3b66f6-c5fc-4bac-b20f-c3ad6fe50178)




