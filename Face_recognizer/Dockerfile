# 베이스 이미지로 Python 3.9 사용
FROM python:3.9-buster

# 필요한 패키지 설치
RUN apt-get update && apt-get install -y \
    build-essential \
    cmake \
    git \
    libgtk2.0-dev \
    pkg-config \
    libavcodec-dev \
    libavformat-dev \
    libswscale-dev \
    python3-opencv \
    && rm -rf /var/lib/apt/lists/*

# RPi.GPIO 설치
RUN pip install RPi.GPIO mysql-connector-python jupyter

# 작업 디렉토리 설정
WORKDIR /app

# 프로젝트 파일 복사
COPY . .

# Jupyter Notebook을 포트 8888에서 실행
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]
