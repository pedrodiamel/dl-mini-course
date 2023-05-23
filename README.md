# Deep Learning Mini Course

## Installation

### Docker

```bash
docker build -f "Dockerfile" -t dlmini:latest .
docker run -ti --privileged --ipc=host --name dlmini-course -p 6006:6006 -p localhost:8080:localhost:8080 -v $DATASETS:/.datasets -v $MODELS:/.models dlmini:latest /bin/bash
```

### Dockercompose

```bash
docker-compose up --build -d
docker-compose down
docker exec -it dl-mini-course /bin/bash
```

### Visdom

```bash
# First install Python server and client
pip install visdom
# Start the server (probably in a screen or tmux)
python -m visdom.server -env_path out/runs/visdom/ -port 6006
# http://localhost:6006/
```

### Jupyter notebook

```bash
jupyter notebook --port 8080 --allow-root --ip 0.0.0.0 --no-browser
```

## References

- [1] <https://github.com/pytorch/tutorials>
- [2] <https://github.com/pytorch/ignite>
- [3] <https://github.com/pytorch/tnt>
- [4] <https://github.com/karpathy/micrograd/>
