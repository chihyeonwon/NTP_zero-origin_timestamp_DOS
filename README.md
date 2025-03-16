# NTP_zero-origin_timestamp_DOS
CVE-2018-7185, CVE-2018-7184에 등재된 NTP zero-origin timestamp denial of service 공격에 대한 분석 보고서 입니다.
```
작성자 : IGLOO Corp, Won Chi Hyun
작성일 : 2025.03.16 
```  
NTP zero-origin timestamp Denial-of-Service NTP 제로 타임스탬프 서비스 거부

ntpd는 인터넷 표준시간 서버 또는 로컬 기준 시간을 통해 시스템의 시간 정보를 동기화하는 운영시스템 데몬이다.
ntpd는 많은 주요 운영 시스템, 라우터 및 인프라 장치와 함께 제공된다.

ntpd에 서비스 거부 취약점이 존재, 이 취약점은 서버에서 timestamp를 처리하는 과정에서 발생하게 된다.   
취약점 코드는 poc 코드에서 타임 스탬프를 업데이트 하기 전에 불량 패킷을 삭제한다.   
이 점을 이용해 공격자는 연관된 데이터를 재설정하고 패킷 내용을 설정하는 zero-origin 타임 스탬프를 대량으로 전송,
서비스 거부를 일으킬 수 있게 된다.
ntp 요청 페이로드에서 timestamp 값이 0인 특징이 있다.
조작된 ntp 요청을 보내 취약점을 발생시킬 수 있으므로 Delete
