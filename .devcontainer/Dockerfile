FROM ubuntu

WORKDIR /root

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update -y \
  && apt-get install -y \
  build-essential \
  curl \
  git \
  libgmp3-dev \
  libncurses5-dev \
  libncursesw5-dev \
  && rm -rf /var/lib/apt/lists/

ENV PATH=/root/.ghcup/bin:/root/.local/bin:$PATH \
    BOOTSTRAP_HASKELL_NONINTERACTIVE=1 \
    BOOTSTRAP_HASKELL_NO_UPGRADE=1 \
    BOOTSTRAP_HASKELL_MINIMAL=1

RUN curl --proto '=https' --tlsv1.2 -sSf https://get-ghcup.haskell.org | sh

RUN ghcup install stack --set 2.15.5 \
  && ghcup install hls --set 2.9.0.1 \
  && ghcup install cabal --set 3.10.3.0 \
  && ghcup install ghc --set 9.4.8

