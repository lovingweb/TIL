# Git Credential Cache

어쩌다 보니 깃헙 계정을 여러 개 사용하게 되었는데, 추가로 만든 계정으로 작업할 때마다 비밀번호를 물어보게 너무 귀찮았다. 그럼에도 불구하고 한동안은 매번 입력했었는데 오늘에서야 그 문제를 해결하고자 마음이 들기 시작했다.

처음에 만든 계정은 좀 오래됐지만 기억을 더듬어보니 ssh key를 등록했던 게 기억나서 보니 역시 새로 추가한 계정에는 ssh key가 등록이 안되어 있다.

빙고~ 하는 마음에 키 값을 복사해서 등록 버튼을 눌러보니 'Key is already in use'가 뜬다. ssh keys는 한 계정에서 한번만 사용할 수 있는가 보다...

자, 그럼 여기서 구글링ㅎ

역시 ssh key를 여러 개 만드는 방법이 나와있다.  
[http://yookeun.github.io/tools/2016/06/26/git-multi-ssh/](http://yookeun.github.io/tools/2016/06/26/git-multi-ssh/){:target="_blank"}

하지만 검색하는 김에 'git 비밀번호'로 검색해보니 간단하게 캐시를 이용하는 방법이 있어서 우선 이 방법을 먼저 써보기로 했다.

* [https://git-scm.com/docs/git-credential-cache](https://git-scm.com/docs/git-credential-cache){:target="_blank"}
* [https://www.devkwon.com/posts/132](https://www.devkwon.com/posts/132){:target="_blank"}

```bash
git config credential.helper 'cache [options]'
```

Git Credential 기능에서 `cache`모드로 설정하면 일정 시간 동안 메모리에 사용자 이름과 암호 같은 인증정보를 기억한다. 이 정보를 Disk에 저장하지는 않으며 메모리에서도 15분(900) 까지만 유지한다.

```bash
git config credential.helper 'cache --timeout=864000'
```

나는 넉넉하게 10일의 정보를 입력했다. 좀 전에 실행하고 이 글을 작성하고 있는데 이후에 수정 및 추가되는 내용이 없다면 성공한 것이겠지.