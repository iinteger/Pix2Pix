# PIX2PIX

* ####  Image-to-Image Translation with Conditional Adversarial Networks

  * 이미지의 Style을 변화시키는 Image-to-Image translation, 즉 Style transfer를 제안함

    

* #### 등장 배경

  * 기존의 GAN은 random noise를 input으로 받기 때문에 무작위 데이터를 생성하게 됨. 따라서 실생활에 적용하기 어려움

  * Colorization을 포함하여 보다 다양한 Domain에 GAN을 적용하고자 함

    

* #### Training

  <img src="images/pix2pix1.png" />

  * CGAN의 구조를 차용하여 이미지 생성에 condition x를 사용하는데, 이때 x는 변환하고자 하는 input image

  * 학습을 진행하면 G는 이미지 y와 비슷한 도메인을 가진 이미지를 생성하도록 학습됨

    <img src="images/pix2pix2.png" />

  * 이때 학습되는 프로세스는 edge를 물체로 변환하거나, colorization, 낮과 밤을 바꾸는 등 매우 다양한 프로세스가 가능함

    

* #### Loss Function

  <img src="images/pix2pix4.png"/>

  

  * 생성한 이미지를 평가할 때 가장 단순한 방법은 각 픽셀의 차이를 더하는 방법 (like L1 loss)

    

    <img src="images/pix2pix3.gif" width=40%/>

    

  * 그러나 전체 픽셀의 관점으로 최적화를 진행하면 모델이 이미지를 대충 뭉뚱그리게 되며, 흐릿해지는 현상이 발생함. 이러한 Blurring은 VAE에서도 나타나는 고질적인 문제로, 모델이 loss의 최소값을 위해 픽셀을 평균값으로 채워버리는 현상

  * Neural-Network 관점에서는 Objective function friendly한 방법이지만, 사람이 볼 땐 실제 이미지와 괴리가 있음

    

  
