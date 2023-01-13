FROM python:3.9-slim AS base

RUN apt-get update -y && \
  apt-get install -y \
  curl

RUN curl -fsSL https://get.pulumi.com | sh

RUN echo -n 'export PATH=$HOME/.pulumi/bin:$PATH' >> ~/.bashrc

ENTRYPOINT []
CMD ["bash"]