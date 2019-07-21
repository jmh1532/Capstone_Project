![title](https://user-images.githubusercontent.com/33171227/61588500-b127ba80-abd7-11e9-87b9-cf6b4bd78a2f.png)
# Safe Fire Exit(Capstone Design)
건물 안에 화재가 발생했을 시, 사람들로 인한 혼잡도와 화재위치를 고려하여 가장 빠른 탈출 경로를 안내하는 어플을 기획. 


### Prerequisites
어플리케이션이 사전에 설치가 되어 있어야하며, 개인적으로 서브메뉴형식으로 타 어플에 들어가길 바람.


## Running the tests
![구성](https://user-images.githubusercontent.com/33171227/61588505-c69ce480-abd7-11e9-9099-88464a35d19a.png)

1. 아두이노 불꽃센서와 온도감지센서를 통한 화재감지(아두이노)
```
아두이노 화재감지 위치 -> 웹서버, 화재위치 DB에 저장
```
2. 웹서버는 이용자에게 어플 푸시메시지, 119에 화재감지 메시지를 전송(웹서버)
```
웹서버(화재위치)- > 어플리케이션
```

3. 어플로 건물안의 비콘을 스캔, 현재 위치정보를 파악(안드로이드)
```
어플리케이션(위치정보) -> 웹서버
```
4.수신한 모든 위치정보를 토대로 혼잡도계산(웹서버)
```
혼잡도가 일정치 이상이 되면 가중치를 부여, 사용자위치정보 DB에 저장
```
5.화재에 대한 가중치와 혼잡도 가중치를 고려한 최단거리 계산(웹서버)
```
Dijkstra 알고리즘 이용한 최단 정점들을 어플리케이션에 전송
```
6. 현재 위치를 기반으로 최단정점들을 이어 길안내UI 표시(안드로이드)
```
3~6번 과정을 탈출할때까지 반복
```
## Screen shot
![webUI](https://user-images.githubusercontent.com/33171227/61588515-e0d6c280-abd7-11e9-9100-9943f847970b.png)

![result](https://user-images.githubusercontent.com/33171227/61588527-05cb3580-abd8-11e9-95fd-7216d41ef56d.png)

## Built With

* [Eclipse](https://www.eclipse.org/downloads/) - using for SpringFrameWork
* [Android Studio](https://developer.android.com/studio/install?hl=ko) - Android
* [MySQL](https://www.mysql.com/) - DataBase
* [ESP8266] - Used to arduino wifi shield
* [BlueTooth4.0] - Beacon = arduino uno + BlueTooth4.0
* [Apache Tomcat](http://tomcat.apache.org/) - server

## Authors

* **정명한** - *Initial work* -
* **심정우**
* **표은영**
* **임주훈**
