# lanit-2022-traffic

#### Task description:

From camera we get only compressed images, what can cause bad keypoints detection, matching and most important bad track reconstruction.
Task was to discover and compare different neural networks that can restore image.
Most chalenging is to create suitable metric for comparing results.

### Стек технологий:

- python

- opencv

- colmap

### Datasets

1. ground truth
 
2. compressed
 
3. restored: 

 results_ARCNN: https://github.com/hkchengrex/PyTorch-ARCNN
 
 results_FBCNN: https://github.com/cszn/DnCNN
 
 results_DNCNN: https://github.com/jiaxi-jiang/FBCNN
 
![image](https://user-images.githubusercontent.com/109301202/189080941-e905c68b-56a0-4926-b81b-a4236f93dae2.png)
![image](https://user-images.githubusercontent.com/109301202/189081050-674db09a-df99-4688-ac89-f571e090711f.png)
![image](https://user-images.githubusercontent.com/109301202/189080864-2c0e4a4a-f3d2-45df-86ba-cd28573f60aa.png)
![image](https://user-images.githubusercontent.com/109301202/189081130-fc4ecd82-323e-4a5a-a8de-5c1f8e026340.png)

### Metrics

1. SSIM, PSNR, PSNR-B:

![image](https://user-images.githubusercontent.com/109301202/189080639-f069d516-7fab-4615-bda3-f5dfb20b6aa0.png)

2. SIFT + BruteForce matching = % cross matches:
![image](https://user-images.githubusercontent.com/109301202/189081470-bc2eb1bb-028f-4598-bfa8-624b0963cf73.png)
![image](https://user-images.githubusercontent.com/109301202/189081719-b2dade49-a931-4941-9983-4d43eb3fe436.png)

(not horizontal lines means not correct matching)

3. SUPERPOINT + SUPERGLUE matching = % cross matches:
![image](https://user-images.githubusercontent.com/109301202/189081865-bb59cd63-80c1-46fb-b065-2917da5fa0d0.png)
![image](https://user-images.githubusercontent.com/109301202/189081969-c2e5718a-e109-4874-a253-52782b9cdc92.png)
![image](https://user-images.githubusercontent.com/109301202/189082007-c054cf94-e787-462f-a2a5-c4c374b30fca.png)
![image](https://user-images.githubusercontent.com/109301202/189082055-ce366c87-20bf-4803-9b75-4e6cc43641ef.png)

(optical flow)

### Seeing bad results on classic matching algorithms, we decided to use coordinates matchings: match only keypoints that located in 1 pixel radius from another keypoint.

![image](https://user-images.githubusercontent.com/109301202/189082853-4169bd3a-efd0-4205-9e9d-2b05d7ea958b.png)

1. SIFT-coord

ARCNN  mean value: 0.482

DNCNN mean value: 0.4975

FBCNN  mean value: 0.5073

2. SUPERPOINT-coord

ARCNN  mean value: 0.1773

DNCNN mean value: 0.1875

FBCNN  mean value: 0.2046

### COLMAP track reconstruction:

metrics from COLMAP: 

1. mean track length

2. mean reprojection error

3. focal length in comparison with ground truth camera params

4. radial distortion in comparison with ground truth camera params

![image](https://user-images.githubusercontent.com/109301202/189085115-0c3c2752-5a57-4ef6-a647-324db0b38bad.png)
![image](https://user-images.githubusercontent.com/109301202/189085157-7a1aaf0c-9613-4bc2-8f2e-977ff0849893.png)
![image](https://user-images.githubusercontent.com/109301202/189085203-fd8c751a-bbc0-49b7-8421-cd1d5a102d35.png)
![image](https://user-images.githubusercontent.com/109301202/189085289-0438a4a9-bfd8-4d99-b581-cd88fe61b342.png)


# feel free to contact with me:

https://t.me/abletobetable

abletobetable@mail.ru
