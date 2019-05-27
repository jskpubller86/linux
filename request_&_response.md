# Request 

시작과 헤더 본문으로 나누며 본문은 있을 수도 있고 없을 수도 있다.

```
- 시작
- 헤더
- 본문
```

시작의 3가지 정보가 들어가며 3가지 정보는 공백으로 구분한다.  시작은 항상 한 줄로 끝난다.

첫번째 정보는 요청의 방식을 나타내며  두번째는 URL 정보가 들어가며 마지막 세번째 정보는 프로토콜이다.

``` request 시작
POST /index.html HTTP/1.1
-> // 방식(method)[공백]URL[공백]HTTP/1.1
```

헤더는 몇 개의 그룹으로 나눌 수 있다. 

일반적으로 Request headers, General headers, Entity headers로 나눈다. 

- Request 헤더 그룹 : 요청의 내용을 좀더 구체화시킨 정보를 담는다.
- Response 헤더 그룹 : 응답의 내용을 좀더 구체화시킨 정보를 담는다.
- General 헤더 그룹 :  메시지 전체에 적용되는 헤더이다.
- Entity 헤더 그룹 :  본문에 대한 정보를 담는다. 본문이 없다면 전송되지 않는다.

```
Accept: text/html,application/xhtml+xml,.....,application/xml;
Accept-Encoding: gzip, deflate
Accept-Language: ko-KR,ko;q=0.9,en-US;q=0.8,en;q=0.7
Cache-Control: max-age=0
Connection: keep-alive
Host: www.ktword.co.kr
Referer: https://www.google.com/
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 6.1; Win64; x64) .... Chrome/74.0.3729.169 Safari/537.36
```



#  Response

```
시작 : HTTP/1.1[공백]200
헤더 : 
본문 : 

```

헤더 :

본문  : 사용자가 보는 내용



# 응답코드 목록

- 1xx 정보

- 2xx 성공

- 3xx 리다이렉트

- 4xx 클라이언트 측 오류

- 5xx 서버 측 오류

#  Cookie 운영 원칙 

1) 중요정보를 담지 않는다.

2) 암호화 해서 저장 (서버에서 암호화)

3) 유효기간, 지속시간 최소화 한다.   ( 유효기간 :  Expired , 지속시간 : MaxAge )

4)  Secure 속성을 활성화한다.  Https 통신을 할 경우에만 사용.

5) HttpOnly 속성을 활성화 한다. HttpOnly 속성이란 클라이언트에서 Cookie 접근을 할 수 업도록 하는 것을 말한다.

# Slowloris 공격 기법

- DoS 공격 기법 중 하나
- 요청 헤더의 끝이 개행문자로 끝나는 요청의 구조를 이용한 공격
- <https://crefunx.tistory.com/search/slowloris>

# 슬로 HTTP POST 공격 = RUDY 공격

- 요청 헤더의 Content-Length의 값을 크게 설정해서 서버가 요청 본문을 기다리도록 하는 공격
- <https://crefunx.tistory.com/35>

# HTTP 응답분할

- 외부입력값을 응답헤더에 값으로 사용하는 경우 
- 개행문자를 이용해서 응답을 여러개로 분할해 전달하고, 
- 분할된 응답 중 본문 영역에 악성행위를 하는 코드를 집어넣어서 공격하는 공격 기법

# 디렉토리 요청할 경우

http://abc.com/data/

1) default page

2) directory listiong 옵션이 활성화 되어 있을 경우 디렉토리 목록을 보여줌.

3)  404 Not Found 

4) static page의 잔재 (예전 클라이언트에게 요청에 대한 응답의 리소스를 다운받게 하기 위한 방법) 























