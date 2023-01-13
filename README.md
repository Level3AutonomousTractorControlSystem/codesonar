#### 레벨3 자율작업 트랙터용 개방형 통합제어 시스템 기술개발: 소프트웨어 품질관리
***
1. 정적분석도구 
```
- CodeSonar version: 5.0
- SW environment: VS2015, GNU C/C++
- project name: AHRS_UI, Tracking_core, Gps_ntrip, Farm_gps_merge
```

```
- SonarQube version: 9.1
- SW environment: Android Studio 4.2.2
- project name: AHRS_UI, CarInfo, radio, WorkingLightInfo
```
***
2. 주요 warnings:
```
- Class: Unresasonable size argument 
- Significance: Security
- File: TcpClient.cpp
- Procedure: CTcpClient::Send
```
```
- Class: Unresasonable size argument 
- Significance: Security
- File: TcpServer.cpp
- Procedure: CTcpServer::Send
```
