# SalEMA

## What SalEMA is

SalEMA is a video saliency prediction network. It utilizes a moving average of convolutional states to produce state of the art results. The architecture has been trained on DHF1K.

## Model

![TemporalEDmodel](https://raw.githubusercontent.com/Linardos/SalEMA/gh-pages/TemporalEDmodel.jpg)

Download our best configuration of the SalEMA model [here (364MB)](https://imatge.upc.edu/web/sites/default/files/projects/saliency/public/VideoSalGAN-II/SalEMA30.pt)

## Installation

- Clone the repo:

```shell
git clone https://github.com/Linardos/SalEMA
```

- Install requirements 
```shell
pip install -r requirements.txt
``` 

## Inference

You may use our pretrained model for inference on either of the 3 datasets: DHF1K [[link]](https://drive.google.com/file/d/1vfRKJloNSIczYEOVjB4zMK8r0k4VJuWk/view), Hollywood-2 [[link]](https://drive.google.com/file/d/1vfRKJloNSIczYEOVjB4zMK8r0k4VJuWk/view), UCF-sports [[link]](https://drive.google.com/drive/folders/1sW0tf9RQMO4RR7SyKhU8Kmbm4jwkFGpQ):

To perform inference on DHF1K validation set:

```shell
python inference.py -dataset=DHF1K -pt_model=SalEMA30.pt -start=600 -end=700 -dst=/path/to/output -src=/path/to/DHF1K/frames
```

To perform inference on Hollywood-2 or UCF-sports test set (because of the way the dataset is structured, it's convenient to use the same path for dst and src):

```shell
python inference.py -dataset=Hollywood-2 -pt_model=SalEMA30.pt -dst=/path/to/Hollywood-2/testing -src=/path/to/Hollywood-2/testing
```

```shell
python inference.py -dataset=UCF-sports -pt_model=SalEMA30.pt -dst=/path/to/UCF-sports/testing -src=/path/to/UCF-sports/testing
```

To perform inference on your own dataset make sure to follow the same structure as DHF1K (numbered folders followed by numbered frames):

```shell
python inference.py -dataset=other -pt_model=SalEMA30.pt -dst=/path/to/output -src=/path/to/your_dataset/frames
```
