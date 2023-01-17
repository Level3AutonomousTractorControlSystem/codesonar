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
- Class: Unresasonable Size Argument 
- Significance: Security
- File: TcpClient.cpp
- Procedure: CTcpClient::Send
```
```
- Class: Unresasonable Size Argument 
- Significance: Security
- File: TcpServer.cpp
- Procedure: CTcpServer::Send
```
```
- Class: Leak 
- Significance: Reliability
- File: parse_position_data.c
- Procedure: parse_position_data
```
```
- Class: Use After Free 
- Significance: Security
- File: tcp_client_c_v2.c
- Procedure: tcp_read_file
```
```
- Class: Uninitializiaed Variable 
- Significance: Security
- File: tcp_client_c_v2.c
- Procedure: func_write
```
```
- Class: File System Race Condition 
- Significance: Security
- File: main.c
- Procedure: main
```
```
- Class: Free Null Point 
- Significance: Redundancy
- File: TcpServer.cpp
- Procedure: tcp_client_c_v2.c
```
```
- Class: Artangent Domain Error 
- Significance: Reliability
- File: update_waypoint_v2.c
- Procedure: Add “if (wp2_lat-wp1_lat !=0 ||wp2_lat-wp1_lat !=0)"
```
```
- Class: Negative File Descriptor 
- Significance: Reliability
- File: tcp_client_c_v2.c
- Changes: Add "if(sock2==-1) return; "
```
