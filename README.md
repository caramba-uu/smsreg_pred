# Conformal prediction enables disease course prediction and allows individualized diagnostic uncertainty in multiple sclerosis

## Steps
<br>

---

### Setting up the environment
To create and activate the environment. <br>
```bash
conda env create -f environment.yml
conda activate websmsreg
```
To export the conda environment to jupyter notebook. <br>
```bash
python -m ipykernel install --user --name=websmsreg
```
<br>

---


### Data preprocessing and creating data splits
The data is collected from Swedish MS REGistry (SMSREG). The data shall be kept in a designated folder. The path to the data is given in the notebook, under input section. [data_cleaning_and_splitting.ipynb](scripts/data_cleaning_and_splitting.ipynb)  <br>
### Training
Training and evaluation of both the model and conformal prediction. [random_forest_cp.ipynb](scripts/random_forest_cp.ipynb) <br>
### Web (title of the web model here)
Model and scripts used for the website model is available in the folder [gradio](gradio).<br>
Run the website locally using

```bash
python3 gradio/app.py
```









## Citation
Please cite:<br>
>Conformal prediction enables disease course prediction and allows individualized diagnostic uncertainty in multiple sclerosis<br>
>Akshai Parakkal Sreenivasan, Aina Vaivade, Yassine Noui, Payam Emami Khoonsari, Joachim Burman, Ola Spjuth, Kim Kultima*<br>
>Status: Submitted.
