FROM python:3.8-slim

# ithingv34 유저 생성(root 유저 X)
RUN mkdir -p /home/ithingv34 \
    && addgroup ithingv34 \
    && useradd -d /home/ithingv34 -g ithingv34 ithingv34 \
    && chown ithingv34:ithingv34 /home/ithingv34

RUN apt-get update \
    && apt-get install -y curl

USER ithingv34
WORKDIR /home/ithingv34

RUN curl -sSL https://install.python-poetry.org | python -

ENV PATH=/home/ithingv34/.local/bin:$PATH

RUN poetry config virtualenvs.in-project true