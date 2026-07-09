# The model was built on Python 3.6 with Mesa 0.8.x; this image
# recreates that environment so the notebooks run as they did in 2019.
# amd64 is required: the pinned 2019-era wheels were never built for arm64.
FROM --platform=linux/amd64 python:3.6-slim

WORKDIR /model

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 8888

# No auth token: intended for local use only. Don't expose this
# container to an untrusted network.
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--no-browser", "--allow-root", "--NotebookApp.token="]
