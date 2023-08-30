# PENN (DBB2023)
Phase Estimation Neural Network on Gene Expression Data (PENN) is a deep learning based method designed for the prediction of unordered gene expression data. 
The architecture of this network is based on the CYCLOPS. However, PENN incorporates the potential periodic oscillation information of the cyclic genes into the objective function to regulate the phase estimation.

PENN's inroduced loss function has two parts. The first part of the equation is the error of fitting observations with the cosine curve using predicted phases considering each gene's geometry. The second part of the loss function is the auto-encoder reconstruction loss.

<img width="762" alt="objectiv" src="https://github.com/aramansary/PENN/assets/71525193/2d3ab2b8-cfdb-4047-b040-8b020d1396d8">

where L<sup>g</sup> is the average level, A<sup>g</sup> is the amplitude, φ<sup>g</sup> is the phase shift and 2π/ω is the period of the g-th eigen-gene. L<sup>g</sup>, A<sup>g</sup>,φ<sup>g</sup> and ω<sup>g</sup> are learnable variables given some initial values and they will be trained through the network. x<sup>^</sup><sub>i</sub> is the output of the auto-encoder for sample i and x<sup>(g)</sup><sub>i</sub> is the input value for gene g and sample i. λ is a balancing factor. 

This repository contains a Keras implemented version of the PENN on mouse liver data [GSE11923](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE11923).
