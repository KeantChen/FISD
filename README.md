# FISD
coda and model for FISD

The code section is the source code of the project, uploaded in the form of a Jupyter notebook, including details of data processing, model training, and testing
The file ending with _data is the code for processing and obtaining training data. The main purpose of the code is

① Convert SMILES into Graph through RDKit,

② Then, Graph obtains FISD through the MLMS model. In this process, Graph is input into the MLMS_MSE and MLMS_COS models separately to obtain a 100-dimensional array, which is then passed through MLMS_2in1 to obtain the final 50-dimensional FISD

③ Then, it binds to the FISD of the protein as the input of VS2Net

*If you want to train an MLMS model from scratch, in addition to the SMILES of the molecule, you also need the corresponding infrared vibration spectrum data of the molecule. We use the QM9 dataset, in which the molecules were optimized at the level of b3lyp/TZVP and frequencies were calculated using the Gaussian16 software program. Subsequently, they were broadened and fragmented to 50 dimensions


The files starting with MLMS_ are the codes for training the MLMS-related models. The details and relevant parameters of the models can be obtained in them, as the data is too large to upload
The files starting with VS2Net_ are the codes for training VS2Net related models


the data section

We will try other ways to upload. If you want to retrain the MLMS model, as long as you have the molecular SMILES and its corresponding IR, you can;

If you want to retrain VS2Net, the FISD of the molecular part can be obtained through MLMS or by using DFT calculations; The FISD of protein needs to be obtained through the MLPS procedure


the Model section

including multiple model parameters involved in the training process

The last saved model during training is

for VS2Net model:

VS2Net.pth,


for MLMS model:

qm9_mse_model.pth,

qm9_cos_model.pth,

qm9_2in1_model.pth

