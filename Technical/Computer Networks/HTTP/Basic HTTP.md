---
Author:
  - zeekbyte
Author Profile:
  - https://linkedin.com/
tags:
  - computer-network
  - http
Creation Date: 2024-07-02T18:16:44+08:00
Last Date: 2024-07-02T18:16:44+08:00
---

## HTTP Basic

### CRLF là gì?
- CR và LF là `control characters`hoặc `bytecode` được sử dụng để đánh dấu kết thúc một dòng trong file text.
    + CR = Carriage Return(`\r`, `0x0D` ở dạng hexadecimal(Thập lục phân), 13 ở dạng decimal(Thập phân)) - Di chuyển con trỏ chuột về đầu dòng mà không tiến tới dòng kế tiếp
    + LF = Line Feed(`\n`, `0x0A` ở dạng hexadecimal, 10 ở dạng decimal) - Di chuyển con trỏ chuột xuống dòng kế tiếp mà không trở lại đầu dòng

- Một CR kết hợp với RF ở sau(`\r\n`, `0x0D0A`) - Di chuyển con trỏ chuột xuống đầu dòng của dòng kế tiếp.


### HTTP Response
- Một HTTP Response bao gồm 3 thành phần, các thành phần được phân tách bởi một CRLF(`\r\n`):
	+ Dòng trạng thái(Status line)
	+ Các Header, được phân tách bằng một CRLF
	+ Response body(Optional)

- ví dụ:
```
HTTP/1.1 200 OK\r\n\r\n
```

- Phân tích:
```
// Status line
HTTP/1.1 			// HTTP Version
200				// Status code
OK				// Optional reason phrase
\r\n				// CRLF đánh dấu kết thúc của status line

// Headers (Empty)

\r\n				// CRLF đánh dấu kếu thúc Headers

// Response body(Empty)
```

### HTTP request
- Một HTTP request gồm có 3 thành phần, các thành phần được phân tách bởi một CRLF (`\r\n`)
	+ Request line
	+ Các Headers(Một Header sẽ được kết thúc bằng một CRLF)
	+ Request body(Optional)

- Ví dụ:
```
GET /index.html HTTP/1.1\r\nHost: localhost:4221\r\nUser-Agent: curl/7.64.1\r\nAccept: */*\r\n\r\n
```

- Giải thích:
```
// Request line
GET				// HTTP Method
/index.html			// Request target
HTTP/1.1			// HTTP Version
\r\n				// CRLF that marks the end of the request line
Host: localhost:4421\r\n  	// Header that specifies the server's host and port
User-Agent: curl/7.64.1\r\n 	// Header that describes the client's user agent
Accept: */*\r\n 		// Header that specifies which media types the client can accept
\r\n 				// CRLF that marks the end of the headers

// Request body(empty)
```