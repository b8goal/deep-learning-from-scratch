##### 날짜 : 2024-03-15 18:49
##### 주제 : #개발환경 #Dockerfile #JupyterNotebook
---
# Memo :
>[!note]

## Dockerfile
```Dockerfile
FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update --yes && \
    # - apt-get upgrade is run to patch known vulnerabilities in apt-get packages as
    #   the ubuntu base image is rebuilt too seldom sometimes (less than once a month)
    apt-get upgrade --yes && \
    apt-get install --yes --no-install-recommends \
    build-essential \
    python3 \
    python3-pip \
    python3-dev \
    python3-venv \
    git \
    && rm -rf /var/lib/apt/lists/*

RUN python3 -m venv /venv
ENV PATH="/venv/bin:$PATH"

RUN pip install --upgrade pip && \
    pip install numpy matplotlib jupyter

RUN jupyter notebook --generate-config && \
    echo "c.NotebookApp.ip = '0.0.0.0'" >> ~/.jupyter/jupyter_notebook_config.py && \
    echo "c.NotebookApp.open_browser = False" >> ~/.jupyter/jupyter_notebook_config.py && \
    echo "c.NotebookApp.allow_root = True" >> ~/.jupyter/jupyter_notebook_config.py

WORKDIR /workspace

CMD [ "bash" ]

```

### Build & Run
```bash
$ docker build -t deep_learning_base -f ./dockerfiles/deep_learning_base.dockerfile .

$ docker run -it --rm -p 8888:8888 --name my_jupyter_notebook -v $(pwd):/workspace deep_learning_base
```

### Run jupyter notebook 
```bash
$ jupyter notebook --ip=0.0.0.0 --allow-root --no-browser
```

## Summary
>[!summary]

# Reference
---
### 출처(참고문헌)
- https://chat.openai.com/share/32d12867-3c95-4129-9c7e-0a6a07313ead
### 연결문서
- 