# Request 

시작과 헤더 본문으로 나누며 본문은 있을 수도 있고 없을 수도 있다.

```
- 시작
- 헤더
- 본문
```

시작의 3가지 정보가 들어가며 3가지 정보는 공백으로 구분한다.  

첫번째 정보는 요청의 방식을 나타내며  두번째는 URL 정보가 들어가며 마지막 세번째 정보는 프로토콜이다.

``` request 시작
POST /index.html HTTP/1.1
-> // 방식(method)[공백]URL[공백]HTTP/1.1
```

헤더는 몇 개의 그룹으로 나눌수 있다. 

일반적으로 Request headers, General headers, Entity headers로 나눈다. 

- Request 헤더 그룹 : 요청의 내용을 좀더 구체화시킨 정보를 담는다.
- Response 헤더 그룹 : 응답의 내용을 좀더 구체화시킨 정보를 담는다.
- General 헤더 그룹 :  메시지 전체에 적용되는 헤더
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





응답코드 목록

1xx 정보

2xx 성공

3xx 리다이렉트

4xx 클라이언트 측 오류

5xx 서버 측 오류



























