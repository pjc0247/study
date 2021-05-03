심화 심화과제
====

* TCP 연결은 송수신하는 데이터 길이를 보장하지 않습니다. 1024바이트를 보내면, 받는쪽에서 1024바이트를 받는게 아니라 512 + 512바이트를 수신할 수도 있다는 뜻입니다.
* 상대방이 보낸 문자열(HTTP REQUEST, JSON, XML)등을 전부 수신하고 완전한 상태에서 파싱할수도 있지만, 대부분의 HTTP 서버는 퍼포먼스를 위해 스트리밍 파싱을 지원합니다.
* 스트리밍 파싱이란 input이 완벽한 형태를 갖추지 않았음에도, 수신된 n바이트 먼저 파싱할 수 있게 하는것입니다.

```tsx
parse('<div');
parse('>Hell');
parse('o World</di');
parse('v>');
```

이전 심화과제에서 만든 파서를 스트리밍 파서로 만들어보세요.

참고
----
* https://github.com/nginx/nginx/blob/master/src/http/ngx_http_parse.c
* https://github.com/ipkn/crow/blob/master/include/crow/http_parser_merged.h
