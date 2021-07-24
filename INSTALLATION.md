# Installation

Start by grabbing this source code:

```
git clone https://github.com/RexYing/gnn-model-explainer
```
## Docker

It is recommended to run from within the provided Docker container, \
or use the Python Virtual Envrionment method below to prevent 
package version conflicts.

**Instructions to Build and Run the container can also be found in the Dockerfile**

To Build:

```
Linux:
sudo docker build --network=host -t nirvash/gnn .

Windows:
docker build -t nirvash/gnn .

```

To Run:

```
To see list of options available for our GNN explainer:
 Linux:
 sudo docker run --rm -v /
     $PWD/:/home nirvash/gnn python3 /home/train.py --help
     
  Windows:
  docker run --rm -v ^ 
      %cd%/:/home nirvash/gnn python3 /home/train.py --help
```

## Python Virtual Environments

It is recommended to run this code inside a `virtualenv` with `python3.7`.

```
virtualenv venv -p /usr/local/bin/python3
source venv/bin/activate
```

### Requirements

To install all requirements, run:

```
pip3 install -r requirements.txt
```

## Manually Install From Source

If you do not want to install using the requirements file, here is what you need:

- PyTorch (tested with `1.3`)

```
pip3 install torch torchvision
```

For alternative methods, check the following [link](https://pytorch.org/)

- OpenCV

```
pip3 install opencv-python
```
Debian/Ubuntu users, if you experience an error with 'libgGL.so',
you may need to install the following:

```
sudo apt install ffmpeg libsm6 libxext6 -y
```


- Misc Required Packages: 

```
pip3 install matplotlib networkx pandas sklearn seaborn
```

- `TensorboardX`

```
pip3 install tensorboardX
```

> TODO: Find which OpenCV dependencies remain, and remove them

To install [RDKit](https://www.rdkit.org/), follow the instructions provided [on the website](https://www.rdkit.org/docs/Install.html).
