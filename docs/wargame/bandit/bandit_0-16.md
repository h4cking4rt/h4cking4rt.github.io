---
title: Bandit_0-16
parent: Bandit
nav_order: 1
---

# bandit 00 ~ 16
{: .no_toc }
[bandit site](https://overthewire.org/wargames/bandit/bandit16.html)

---  

## Table of Contents
{: .no_toc .text-delta }

- TOC
{:toc}

---  

## Level 0  

> ssh 접속

```ssh <remote-address> [-l login_name] [-p port] ```

또는

```ssh <username>@<remote> -p <port>```  
  
	  
  - 참고  
  
	[SSH메뉴얼](https://manpages.ubuntu.com/manpages/noble/man1/ssh.1.html)

---

## Level 0 → Level 1  

> readme 파일 확인하기

`ls -l`

- `-`  : 파일 형태
- `d` : 디렉토리 형태

`cat <filename>` 

<details>
	<summary>password</summary>
	
    	ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
	
</details>

  - 참고

	[ls메뉴얼](https://manpages.ubuntu.com/manpages/noble/en/man1/ls.1.html)

	[cat메뉴얼](https://manpages.ubuntu.com/manpages/noble/en/man1/cat.1.html)

---

## Level 1 → Level 2  

> 파일이름이 - 일 때  

​	`cat -` : 표준 입력을 출력. - 파일의 내용을 출력할 수 없음

​	`cat ./-` : 현재 디렉토리 하의의 - 파일 출력 

​	또는

​	 `cat < -`  : cat 에 - 파일 내용 리다이렉션

<details>
	<summary>password</summary>
    	263JGJPfgU6LtdEvgfWU1XP5yac29mFx
</details>

---

## Level 2 → Level 3  

> 파일 이름에 공백이 있을 때

​	`cat 'filename with space'`

​	또는

​	`cat filename\ with\ space`

<details>
	<summary>password</summary>
    	MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
</details>

---

## Level 3 → Level 4  

> 숨겨진 파일

​	`ls -l`

<details>
	<summary>password</summary>
    	2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
</details>

---

## Level 4 → Level 5  

> 사람이 읽을 수 있는 파일

`file` : 파일의 종류 알려줌

`file ./*` : 해당 디렉터리 하위의 모든 파일

ASCII text : 순수 텍스트만 포함되어 있는 파일

<details>
	<summary>password</summary>
	
    	4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
	
</details>

  - 참고

	[file 메뉴얼](https://manpages.ubuntu.com/manpages/oracular/en/man1/file.1posix.html)

---

## Level 5 → Level 6  

> - human-readable
> - 1033 bytes in size
> - not executable

`find <경로> -size 1033c` : 1033 byte 크기의 파일을 경로 하위에서 찾음

<details>
	<summary>password</summary>
    	HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
</details>

  - 참고

	[find메뉴얼](https://manpages.ubuntu.com/manpages/oracular/en/man1/find.1posix.html)

---

## Level 6 → Level 7  

> - somewhere on the server
> - owned by user bandit7
> - owned by group bandit6
> - 33 bytes in size

`find` 옵션

​	`-user <username>`  : 소유자로 검색

​	`-group <groupname>` : 소유그룹으로 검색

Permission denied 가 너무 많이 뜰 때

​	`2>>/dev/null` 붙여주면 에러 제외하고 검색 가능

<details>
	<summary>password</summary>
    	morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
</details>

---

## Level 7 → Level 8  

> **data.txt** 파일 속 **millionth** 라는 단어 옆에 패스워드

`grep <문자열> <파일>` : 파일 안에서 문자열이 들어간 행을 출력

<details>
	<summary>password</summary>
    	dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
</details>

  - 참고

	[grep메뉴얼](https://manpages.ubuntu.com/manpages/noble/en/man1/grep.1.html)

---

## Level 8 → Level 9  

> **data.txt** 파일 안에서 한번만 나오는 줄

`sort` : 정렬

`uniq` : 중복 처리

​	`uniq -u` : 중복 없는 라인만 출력

<details>
	<summary>password</summary>
    	4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
</details>

  - 참고

  [sort메뉴얼](https://manpages.ubuntu.com/manpages/noble/en/man1/sort.1.html)

	[uniq메뉴얼](https://manpages.ubuntu.com/manpages/noble/en/man1/uniq.1.html)

---

## Level 9 → Level 10  

> **data.txt** 파일 안에서 여러개의 '='가 앞에 들어간, 사람이 읽을 수 있는 문장

`strings` : 문자열을 검색하고 출력

`grep` 과 결합해서 사용

<details>
	<summary>password</summary>
    	FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
</details>

  - 참고

	[stirings메뉴얼](https://manpages.ubuntu.com/manpages/noble/en/man1/strings.1posix.html)

---

## Level 10 → Level 11  

> **data.txt** 파일 안에서 base64로 인코딩된 데이터

`base64 -d`  : base64로 인코딩된 데이터를 디코딩

<details>
	<summary>password</summary>
    	dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
</details>

  - 참고

	[base64메뉴얼](https://manpages.ubuntu.com/manpages/noble/en/man1/strings.1posix.html)

---

## Level 11 → Level 12  

> **data.txt** 파일 안에서 패스워드가 모든 소문자(a-z)와 대문자(A-Z)가 각각 13자리씩 회전(ROT13)

`tr` : 특정문자를 변환하거나 삭제

`tr '[a-z]' '[n-za-n]'` : abcdefghijklmnopqrstuvwxyz 를 각각 nopqrstuvwxyzabcdefghijklm 로 변환

<details>
	<summary>password</summary>
    	7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
</details>

  - 참고

	[tr메뉴얼](https://manpages.ubuntu.com/manpages/noble/en/man1/tr.1posix.html)

	[ROT13에 대하여](https://en.wikipedia.org/wiki/ROT13)

---

## Level 12 → Level 13  

> -  **data.txt** 파일에 패스워드 있음
> - 여러번 압축된 hexdump 파일
> - `/tmp` 디렉토리 하위에 작업 디렉토리 만들기
> - `mkdir` 을 이용하여 추측하기 어려운 이름의 디렉토리를 만들거나, `mktemp -d` 로 생성하여 디렉토리 이동시키기 

`mktemp -d` : 안전한 이름의 임시 디렉토리 생성하고 이름 출력

`xxd -r [파일] > [저장할파일명]`  : hexdump 파일을 바이너리 파일로 변환

`file` : 파일의 형식 확인

`gzip -cd [파일] > [저장할파일명]` : gzip 파일 압축해제

`gzip -d [파일]` : gzip 파일 압축해제. 확장자가 .gz 이어야 하며, 원본 파일이 복원됨(압축파일 삭제됨)

`zcat [파일] > [저장할파일명]` : `gzip -cd` 와 같음.

`bzip2 -cd [파일] > [저장할파일명]` : bzip2 파일 압축해제

`tar -xvf [파일]` : tar 파일 압축해제 (v : 파일설명, x : 파일추출, f : 압축파일 지정)



<details>
	<summary>디렉토리 이름 및 password</summary>
      디렉토리 이름 : /tmp/tmp.dguLvEeKt5<br>
    	패스워드 : FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
</details>

  - 참고

	[Hex dump - Wikipedia](https://en.wikipedia.org/wiki/Hex_dump)

	[xxd메뉴얼](https://manpages.ubuntu.com/manpages/noble/en/man1/xxd.1.html)

	[gzip,zcat메뉴얼](https://manpages.ubuntu.com/manpages/oracular/en/man1/gzip.1.html)

	[bzip2메뉴얼](https://manpages.ubuntu.com/manpages/noble/en/man1/bzip2.1.html)

	[tar메뉴얼](https://manpages.ubuntu.com/manpages/noble/en/man1/tar.1.html)

---

## Level 13 → Level 14  

> - 패스워드는 **/etc/bandit_pass/bandit14** 에 있음
> - bandit14 계정만 읽을 수 있음
> - private SSH key 를 이용해서 다음 레벨 로그인

`ssh -i [private key(경로포함)]` : private ssh key 이용해서 로그인

<details>
	<summary>password</summary>
    	패스워드 : MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
</details>

---

## Level 14 → Level 15  

> **port 30000 on localhost** 에 키 존재

`nc <hostname> <port>` : tcp / udp 연결

`telnet <hostname> <port>` : tcp 연결 

<details>
	<summary>password</summary>
    	패스워드 : 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
</details>

  - 참고

	[nc메뉴얼](https://manpages.ubuntu.com/manpages/focal/en/man1/nc.traditional.1.html)

	[telnet메뉴얼](https://manpages.ubuntu.com/manpages/xenial/man1/telnet-ssl.1.html)

---

## Level 15 → Level 16  

>**port 30001 on localhost** 에 SSL/TLS 암호화를 통해 연결하면 암호 획득

`ncat --ssl <hostname> <port>` : SSL/TLS 연결

`openssl s_client -connect <hostname>:<port>` : SSL/TLS 연결 

<details>
	<summary>password</summary>
    	패스워드 : kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
</details>

  - 참고

	[ncat메뉴얼](https://manpages.ubuntu.com/manpages/noble/en/man1/ncat.1.html)

	[openssl메뉴얼](https://manpages.ubuntu.com/manpages/noble/en/man1/openssl.1ssl.html)

	[openssl-s_client메뉴얼](https://manpages.ubuntu.com/manpages/noble/en/man1/openssl-s_client.1ssl.html)


