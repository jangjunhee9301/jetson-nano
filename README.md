# 젯슨나노
![젯슨나노](https://github.com/user-attachments/assets/e0379a47-586b-4477-9721-cbfc362b87a0)


# ㅣGetting Started with AI on Jetson Nanoㅣ


#### 1. Jetson Nano Setting 준비물
    
```
        - jetson nano 4gb
        ![IMG_1235](https://github.com/user-attachments/assets/4aeaaf84-6b90-47f9-859f-685096610775)

        - c type power adapter
  
        - 와이파이 동글
  
        - 웹캠(USB Camera), 또는 CSI Camera (라즈베리파이 V2)
  
        - 64기가 이상 마이크로sd카드
  
        - 그외 쿨링펜, lcd, 또는 모니터. hdmi
```
 

#### 2. jetson nano에 대하여

<b>  welcome 부터 따라하기
       https://learn.nvidia.com/courses/course?course_id=course-v1:DLI+S-RX-02+V2&unit=block-v1:DLI+S-RX-02+V2+type@vertical+block@aba5104413ae454c8c63a6f301925337

#### 3. jetpack downloads 
  
<b>      https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit#write

#### 4. 이미지  굽기 위해 필요한 것들
![발레나 엣쳐](https://github.com/user-attachments/assets/4f900dc3-9fa3-4fdb-85a0-24c0dc163156)
![발레나 엣쳐 1](https://github.com/user-attachments/assets/7ecdb9c1-9dac-4bd9-9e83-f2618513e90b)


       4-1. sd card formatter  download
       4-2. balenaetcher download --->  이미지 굽기
       4-3. 제슨나노에 sd넣고 우분투 설치
       
#### 5. 제슨 알아보고 설치하기
  
  [https://developer.nvidia.com/embedded/learn/jetson-nano-2gb-devkit-user-guide#id-.JetsonNano2GBDeveloperKitUserGuidevbatuu_v1.0-DeveloperKitSetup](https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit#write)

#### 6. 우분투 설치

![우분투 설치 1](https://github.com/user-attachments/assets/c3affbea-f328-4968-9692-617061d34a0f)
![우분투 설치 2](https://github.com/user-attachments/assets/c0fed95c-3521-43a8-9764-082bdde16d0a)
![우분투 설치 3](https://github.com/user-attachments/assets/e97d62d2-f0e1-4756-87fe-e92614e2f381)

#### 7. 온도
 확인과 쿨링팬
***
jtop : system monitoring tool
terminal 열기
```
sudo apt install python3-pip
sudo -H pip3 install -U jetson-stats
```
만약 에러가 뜨면 sudo apt-get upgrade, sudo apt-get update해준다.
jetson-stats-4.2.3 가 써진 걸 확인.
이제 온도를 확인하자
```
reboot
jtop
```
이제 쿨링팬을 돌려보자
```
sudo sh -c 'echo 128 > /sys/devices/pwm-fan/target_pwm'
```
다시 온도를 확인해보자. 온도가 많이 떨어진다.

#### 8. 카메라
***
카메라를 인식하고 실행하자.
```
~$  ls /dev/vi*
~$ git clone https://github.com/jetsonhacks/USB-Camera.git
~$ cd USB-Camera
python3 usb-camera-gst.py
```
