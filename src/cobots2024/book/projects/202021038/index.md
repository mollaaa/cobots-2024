# 로봇 팔을 활용한 분리수거 자동화

## 프로젝트 개요

이 프로젝트는 ROS2 기반으로 한 두산 로보틱스 협동로봇을 활용하여 분리수거를 자동화하는 시스템을 구현하는 것을 목표로 한다. 이 시스템은 쓰레기를 감지하고 구분하여 재활용 가능한 항목을 분리수거함에 배치하여 환경 보호와 재활용을 촉진한다.

## 프로젝트 목표

1. 로봇 팔을 사용하여 주변 환경을 모니터링하고 쓰레기를 감지한다.
2. 쓰레기를 캔, 패트, 플라스틱, 종이 등으로 분류하여 자동으로 분리수거 한다.
3. 분리된 재활용품을 정확하게 배치하여 환경 보호와 재활용을 촉진한다.

## 방법론

- 로봇 프로그래밍 및 시뮬레이션: 로봇 팔을 제어하기 위한 프로그램을 개발하고 시뮬레이션 환경에서 테스트한다.
- 쓰게리 선별 알고리즘 구현: 컴퓨터 비전 기술을 활용하여 쓰레기를 식별하고 분류하는 알고리즘을 구현한다.
- 파이프라인 구축: 쓰레기 선별 및 분리수거 과정을 자동화하기 위한 통합 시스템을 구축한다.

## 필요 자원

- 하드웨어 : 두산 협동 로봇, 카메라, 기타 센서
- 소프트웨어 : ROS2, OpenCV 물체 분류 및 인식을 위한 컴퓨터 비전 라이브러리
- 
## 프로젝트 참여자
- 학번 : 202021038
- 이름 : 홍성관
- E-mail : 202021038@chu.ac.kr

## 예상 예산

|품목  | 가격(원)|
| ---- | ----- |
| 카메 | 35,000 |
| **총 예산** | **35,000** |

## 예상 일정(총 기간:8주)

|주차   |활동       |
| ------ | ------------------ |
|주 1-2 | 프로젝트 계획 및 초기 설계|
|주 3-4 | 로봇 프로그래밍 및 시뮬레이션|
|주 5-6 | 쓰레기 선별 알고리즘 구현 및 파이프라인 구축|
|주 7 | 테스트 및 피드백|
|주 8 | 최종 발표, 프로젝트 마무리 및 문서화|

## 위험관리

기술적인 부족함을 보완하기 위해 꾸준한 학습과 함께 필요한 경우 전문가의 도움을 받아 프로젝트에 필요한 기술을 확보하고, 유연한 일정 관리와 정기적인 평가를 통해 일정 지연을 최소화한다.

## 숙제
- !![스크린샷 2024-05-21 155618](https://github.com/chu-aie/cobots-2024/assets/133960401/1f6ab0be-0499-4aee-a1ff-765e827b9fba)

## 기말 과제
Jupyter Notebook 프로토타입 제작 중 오류를 해결하지 못하여 turtlesim 실행하기로 하였다.
![화면 캡처 2024-06-22 233516](https://github.com/chu-aie/cobots-2024/assets/133960401/96c4a2b5-f8c4-467f-8bed-169eb4a22f31)
![화면 캡처 2024-06-22 233529](https://github.com/chu-aie/cobots-2024/assets/133960401/c8a8e3b2-deab-4334-bb7f-68d8cd8fff95)

turtlesim 실행
- git 명령어를 통해 ros_tutorials git repository를 colone 하여 저장소 복제
~/dev_ws/src$ git clone https://github.com/ros/ros_tutorials.git -b dashing-devel

Cloning into 'ros_tutorials'...
remote: Enumerating objects: 9, done.
remote: Counting objects: 100% (9/9), done.
remote: Compressing objects: 100% (8/8), done.
remote: Total 2689 (delta 3), reused 3 (delta 1), pack-reused 2680
Receiving objects: 100% (2689/2689), 574.30 KiB | 678.00 KiB/s, done.
Resolving deltas: 100% (1620/1620), done.

- ros_tutorials로 이동하여 colcon으로 빌드
~/dev_ws/src/ros_tutorials$ colcon build
Starting >>> turtlesim
Finished <<< turtlesim [0.63s]

Summary: 1 package finished [0.84s]

-bash 환경 파일인 setup.bash 을 실행하여 빌드된 package 설치
~/dev_ws/src/ros_tutorials$ source ./install/setup.bash

- ros2 build 명령어로 turtlesim 패키지의 turtlesim_node 노드를 실행

~/dev_ws/src/ros_tutorials$ ros2 run turtlesim turtlesim_node
<img width="374" alt="img" src="https://github.com/chu-aie/cobots-2024/assets/133960401/ab77f615-2602-451e-857a-d39e512d4b0c">

- turtle 을 이동하기 위해서, turtlesim 패키지의 turtle_teleop_key 노드를 실행

- 키보드의 방향키를 누르면 turtle 조작 가능
  ~/dev_ws/src/ros_tutorials$ ros2 run turtlesim turtle_teleop_key
Reading from keyboard
---------------------------
Use arrow keys to move the turtle.
Use G|B|V|C|D|E|R|T keys to rotate to absolute orientations. 'F' to cancel a rotation.
'Q' to quit.
