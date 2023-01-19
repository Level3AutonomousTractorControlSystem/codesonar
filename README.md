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
- Class: Leak 
- Significance: Reliability
- File: parse_position_data.c
- Procedure: parse_position_data
- Changes: Add "free(mtx);"
```
```
- Class: Use After Free 
- Significance: Security
- File: tcp_client_c_v2.c
- Procedure: tcp_read_file
- Changes: Move “fsize=ftell(file3);” to the inside of if-else clause
```
```
- Class: Uninitializiaed Variable 
- Significance: Security
- File: tcp_client_c_v2.c
- Procedure: func_write
- Changes: Add "remainSize_send=0;"
```
```
- Class: File System Race Condition 
- Significance: Security
- File: main.c
- Procedure: main
- Changes: Replace malloc() with calloc()
```
```
- Class: Free Null Point 
- Significance: Redundancy
- File: TcpServer.cpp
- Procedure: tcp_client_c_v2.c
- Changes: Add "if(file_buf != NULL)"
```
```
- Class: Artangent Domain Error 
- Significance: Reliability
- File: update_waypoint_v2.c
- Procedure: update_waypoint_v2
- Changes: Add “if (wp2_lat-wp1_lat !=0 ||wp2_lat-wp1_lat !=0)"
```
```
- Class: Negative File Descriptor 
- Significance: Reliability
- File: tcp_client_c_v2.c
- Procedure: tcp_client_param_block_v2_2
- Changes: Add "exit(1);"
```
```
- Class: Float Division By Zero 
- Significance: Reliability
- File: update_waypoint_v2.c
- Procedure: calculate_control_point
- Changes: Add "if(wp2_lon_new-wp1_lon != 0)"
```
```
- Class: Buffer Overrun 
- Significance: Security
- File: main.c
- Procedure: main
- Changes: Replace sprintf() with snprintf()
```
```
- Class: Coercion Alter Value 
- Significance: Reliability
- File: tcp_client_c_v2.c
- Procedure: tcp_client_param_block_v2_2
- Changes: Add "exit(1);"
```
```
- Class: Null Pointer Dereference 
- Significance: Reliability
- File: parse_rddf.c
- Procedure: parse_rddf
- Changes: Add "if(pto_raw == NULL) return -1;"
```
```
- Class: Add a nested comment explaning why this method is empty, throw an UnsupportedOperationException or complete the implementation 
- Severity: CodeSmell - Critical
- File: gps_proc.py
- Procedure: gps_proc
- Changes: Add a comment with explain
```
```
- Class: Specify an exception class to catch or reraise the exception 
- Severity: CodeSmell - Critical
- File: img_proc.py
- Procedure: image_gps_stiching
- Changes: Add "print("image_gps_stiching_error")" within the exception clause
```
```
- Class: Refactor this function to reduce its Cognitive Complexity from 19 to the 15 allowed 
- Severity: CodeSmell - Critical
- File: main.py
- Procedure: main
- Changes: Create a method, and move the codes, "ready(ctx)" "image, lat, long = open_gps_image(ctx)" "perform(ctx, image, lat, long)", in it
```
```
- Class: Define a constant instead of duplicating this literal "bird's-eye" 5times 
- Severity: CodeSmell - Critical
- File: main.py
- Procedure: main
- Changes: Add "birdeyeview="bird's-eye""
```
```
- Class: Reraise this exception to stop the application as the user expects 
- Severity: CodeSmell - Critical
- File: main.py
- Procedure: main
- Changes: Chage "pass" to "raise"
```
```
- Class: Either re-interrupt this method or rethrow the "InterruptedException" that can be caught here 
- Severity: CodeSmell - Critical
- File: ArixRadioActivity.java
- Procedure: sendBroadcastToMusincPause
- Changes: Add "Thread.current.Tread().interrupt();"
```
