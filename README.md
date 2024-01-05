<!-- ![header](https://capsule-render.vercel.app/api?type=wave&color=auto&height=150&section=header&text=JinhyeonKwak%20&fontSize=30)
-->
### 👋 곽진현 (JinhyeonKwak) 👋
---
어떠한 문제라도 두려움 없이 부딪힐 수 있는 개발자가 되기 위해 노력하고 있습니다. <br>
*Java*와 *Spring*을 활용한 다수의 프로젝트를 진행하였고, Java Swing을 이용해 간단한 GUI 애플리케이션을 만든 경험이 있습니다.

현재, _신한투자증권 프로 디지털 아카데미_ 3기 교육과정을 밟고 있습니다. (2023.12.27 ~ 2024.06.27)

<br>
  
![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=JinhyeonKwak&show_icons=true&theme=prussian)
<br>
<br>
[![Solved.ac Profile](http://mazassumnida.wtf/api/v2/generate_badge?boj=wlsgus555)](https://solved.ac/wlsgus555/)
<br>
<br>

## 🛠️ 기술 스택
<p align="left">
  <img src="https://img.shields.io/badge/java-007396?style=for-the-badge&logo=java&logoColor=white">
  <img src="https://img.shields.io/badge/spring-6DB33F?style=for-the-badge&logo=spring&logoColor=white">
  <img src="https://img.shields.io/badge/swift-F05138?style=for-the-badge&logo=swift&logoColor=white">
  <img src="https://img.shields.io/badge/amazon ec2-FF9900?style=for-the-badge&logo=amazon ec2&logoColor=white">
  <img src="https://img.shields.io/badge/amazon rds-527FFF?style=for-the-badge&logo=amazon rds&logoColor=white">
</p>

## AWS 인스턴스 유형, 패밀리 등에 따른 성능 측정
### 성능 측정 방법
1. 실행 시간 : 구동되고 있는 서버에 api 요청을 한 번에 10개를 보내어 실행 시간을 측정함.
2. CPU 이용률 : 인스턴스 콘솔에서 모니터링 툴을 이용함.
```
#!/bin/bash

# Check if API_URL parameter is provided
if [ -z "$1" ]; then
    echo "Usage: $0 <API_URL>"
    exit 1
fi

# Number of concurrent requests
NUM_CONCURRENT_REQUESTS=10

# Your API endpoint
API_URL="$1"  # Assuming HTTP, change to https if needed

rm -f response_files/response_*.html

# Directory to save response files
RESPONSE_DIR="response_files"

# Create the directory if it doesn't exist
mkdir -p "$RESPONSE_DIR"

# Function to make an HTTP request and save response to a file
make_request() {
    response=$(curl -s "$API_URL")
    if [ -n "$response" ]; then
        filename="$RESPONSE_DIR/response_$RANDOM.html"
        echo "$response" > "$filename"
        echo "$filename"
    else
        echo "Failed to fetch response from $API_URL"
    fi
}

# Simulate concurrent requests and save responses to files
for ((i = 1; i <= NUM_CONCURRENT_REQUESTS; i++)); do
    response_file=$(make_request)
    if [ -n "$response_file" ]; then
        echo "Response for request $i saved to: $response_file"
    fi
done
```
![image](https://github.com/JinhyeonKwak/JinhyeonKwak/assets/93817551/a20db6a1-ccf2-4855-91ce-418d1ddc6437)
![image](https://github.com/JinhyeonKwak/JinhyeonKwak/assets/93817551/4145c3e0-de9f-47ea-90fb-8ccf514bdbfb)
