<h1 align="center">스마트 물류 자동화 시스템 프로젝트 AIServer 💻 </h1>

## 🛠️ 기술 스택

<img src="https://img.shields.io/badge/Python-3776AB?style=round&logo=Python&logoColor=white" /> <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=round&logo=opencv&logoColor=white" /> <img src="https://img.shields.io/badge/Flask-000000?style=round&logo=Flask&logoColor=white" />

## 🤹🏻 기술 스택 선정 이유

- Python :
  Python은 다목적 프로그래밍 언어로 다양한 분야에서 사용되며, 데이터 과학, 기계 학습, 웹 개발, 자동화 등 다양한 응용 분야에서 활용되는 범용 언어입니다. 풍부한 라이브러리와 프레임워크 지원으로 빠른 개발과 유지 관리가 가능하며, 데이터 처리와 분석에도 용이합니다.

- OpenCV : OpenCV는 컴퓨터 비전 및 이미지 처리를 위한 라이브러리로, 이미지 및 비디오 데이터 처리와 분석에 필수적입니다. Python과의 통합이 우수하며, 복잡한 이미지 처리 작업을 간단하게 수행할 수 있습니다.

- Flask : Flask는 가벼우면서도 강력한 웹 프레임워크로, 웹 애플리케이션을 빠르게 개발하고 배포하는 데 적합합니다. Python과의 통합이 원활하며, RESTful API를 구축하고 웹 애플리케이션을 구현하는 데 사용됩니다.

## 📌 프로젝트 목표

```sh
컨베이어 벨트 위 카메라로부터 이미지를 받아와서 물류의 QR코드를 인식하고 처리하는 프로젝트입니다.

QR 코드가 성공적으로 인식하면 QR코드 영역에 바운딩 박스가 생기고 QR코드의 데이터가 DB에 저장되는 프로젝트 입니다.

Flask를 활용해서 IoT 장비로부터 카메라 이미지를 업로드하고 프론트엔드에서 QR코드를 처리한 이미지를 받아갑니다.
```

## 🔍 Overview

<center>
    <img src="./img/qr.gif" />
</center>

### 1. QR코드 처리

```sh
QR코드를 처리하기 위해 pyzbar 라이브러리를 사용합니다.

이를 통해 QR코드를 인식하고, 해당 QR코드에는 물류 데이터 (상자, 상자 내 제품)가 포함되어 있습니다.

QR코드가 인식되면 OpenCV를 이용해서 해당 영역 주위에 경계 상자가 그려집니다.

인식된 QR코드의 데이터를 백엔드로 전송하여 데이터베이스에 저장합니다.

이를 통해 물류 정보를 실시간으로 관리하고 추적할 수 있습니다.
```

<br>

### 2. 이미지 업로드 및 배포

```sh
Flask를 사용하여 IoT 카메라 장비로부터 이미지를 업로드하는 URL을 제공합니다.

이를 통해 IoT 카메라 장비는 이미지를 서버에 업로드할 수 있으며, 프론트엔드는 업로드된

이미지를 받아올 수 있는 URL을 통해 이미지를 표시합니다.

이를 통해 이미지 데이터를 쉽게 관리하고 프론트엔드와 AIServer 간에 이미지를 전달합니다.
```

<br>

## 📄 Flask 요구사항 명세서

### 1. 업로드 기능

```sh
POST /upload

IoT 카메라에서 POST 요청을 통해 사진을 업로드합니다.
```

<br>

### 2. 클라이언트가 이미지를 받아가기

```sh
GET /stream

클라이언트는 GET 요청을 사용하여 이미지를 다운로드합니다.
```
