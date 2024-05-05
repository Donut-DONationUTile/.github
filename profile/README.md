# DONUT-DONationUTile [![APK file](https://img.shields.io/badge/-APK%20file-blue)](https://drive.google.com/file/d/1g9B9qp6Sc10ojrjxJZ483lGM3o34yWJt/view?usp=sharing)

>_“A shilling is the measure of less pleasure, or satisfaction of any kind, to a rich man than to a poor one. The happiness which an additional shilling brings to a poor man is much greater than that which it brings to a rich one.”_
</br></br>_- Principles of Economics (8th ed.) PLL v6.0 (generated September, 2011) 16 -_

</br>

## Overview
[![Demo Video](https://img.youtube.com/vi/YRxP1OyxY9E/0.jpg)]([https://youtu.be/YRxP1OyxY9E](https://youtu.be/qjlmdKrCPaI))

  `DONUT` is a sustainable donation platform tailored to the developmental characteristics of adolescents, providing a stigma-free process for beneficiaries. </br></br>
  By utilizing unused resources such as gift vouchers, amounting to 900 million KRW annually in South Korea, it facilitates low-income youth to purchase groceries and essential items.

</br>

## Table of Contents
  - [Sustainable Development Goals (SDGs)](#Sustainable-Development-Goals-SDGs)
  - [Architecture](#Architecture)
  - [How to Run](#How-to-Run)
  - [Demo Video](#Demo-Video)
  - [How to Use DONUT](#How-to-Use-DONUT)
  - [TEAM ZPE (0.8)](#TEAM-ZPE-(0.8))

</br>

## Sustainable Development Goals (SDGs)
| [1] No Poverty                                                                                                              | [12] Responsible Consumption and Production |
|-----------------------------------------------------------------------------------------------------------------------------|--------------------------------------------|
| <img src="https://github.com/Donut-DONationUTile/.github/assets/79368467/2eb097ef-2c68-439f-a080-76c8328cb457" width="400"> | <img src="https://github.com/Donut-DONationUTile/.github/assets/79368467/51c7f9e8-cbec-46d1-865e-e615e5548261" width="400"> |
| End poverty in all its forms, everywhere.                                                                                   | Ensure sustainable consumption and production patterns. |


</br>

## Architecture

<image src='https://github.com/Donut-DONationUTile/.github/assets/79368467/8414eb2e-fea3-46b1-9caf-e4ab372dfa8d?raw=true' width="800"/>
</br></br>

#### DONUT is comprised of a Client Application, Web Server, Database, Storage, and AI Server.
  The Client Application is implemented on `Android` using `Kotlin`, with the MVVM architecture to separate UI logic from business logic and increase code reusability and scalability. Through various interactions with users, the Client Application forwards requests to the Web Server.
  </br></br>
  The Web Server processes client requests and can communicate with the AI Server in need. It is implemented based on `Spring Boot` and utilizes `Redis` for JWT processing. Both Spring Boot and Redis are deployed in `Docker` containers via `GCP` Compute Engine. CI/CD is established using GCP Code Build and Artifact Registry for agile development.
  </br></br>
  A `MySQL` 8.0-based GCP Cloud SQL instance serves as the main Database. GCP Cloud Storage is used for the Image bucket, where URLs of inserted objects are stored in the Database.
  </br></br>
  The AI Model, served by `FastAPI`, is hosted on a separate VM from the Web Server. It is also deployed using Docker in preparation for utilizing `Kubernetes` for resource management caused by an increase in the number of users. Low-resolution gift card images forwarded from the Web Server to the AI Server are enhanced to high resolution using `TensorFlow`’s ESRGAN model and then stored in the GCP Storage bucket. The URLs of the stored objects are also updated in the Database.


</br>

## How to Run - Client

### Requirements
#### Software requirement

- Android studio Flamingo 2022.2.1
- compileSdk 34 or higher
- minSdk 33 or higher

#### Hardware requirement

- CameraX supported Android Device within [this link](https://developer.android.com/media/camera/camerax/devices)
(CameraX is supported on most Android devices running Android 5.0 (API level 21) and higher.)


1. Check the requirement above.
2. Download the [APK file](https://drive.google.com/file/d/1g9B9qp6Sc10ojrjxJZ483lGM3o34yWJt/view?usp=sharing) on your Android device.
3. Run the apllication from APK file

</br>

## How to Run - Server

1. sudo docker pull `kang1221/donut`
2. sudo docker tag `kang1221/donut donut`
3. sudo docker-compose up

</br>

## How to Use DONUT
<image src='https://github.com/akimcse/akimcse/assets/63237214/3a45c6dd-414e-4b8e-9b61-553411aca83a' width="800"/>

</br>
</br>

## TEAM ZPE (0.8)

|                                    Client                                     |                                    Server                                     |                                 AI & Server                                  |                                UX & UI Design                                |
|:-----------------------------------------------------------------------------:|:-----------------------------------------------------------------------------:|:----------------------------------------------------------------------------:|:----------------------------------------------------------------------------:|
|                    [Hyuna Kim](https://github.com/akimcse)                    |                   [Ganghee Lee](https://github.com/Ganghee-Lee-0522)                   |                [Yeonsoo Kang](https://github.com/Kang1221)                |                                [Sohyun Kim](https://www.behance.net/kimsh9181fabf)                                |

