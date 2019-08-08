---
layout: post
title:  "Jekyll 블로그 LiveReload(자동 새로고침) 기능을 사용해보기"
date:   2019-08-08 10:00:00 +0900
comments: true
categories: programming
tags: jekyll tip
image: /assets/images/posts/20190808/5.png
---
Jekyll은 개발 서버도 내장하고 있어, 로컬에서 브라우저로 접속하여 사이트가 어떻게 생성될 지 미리 살펴 볼 수 있다.[^jekyll]
기본 Jekyll 테마를 커스터마이징 하거나 검색엔진 최적화(SEO), 플러그인 추가 등을 위해서는 로컬에서 테스트 하는 과정은 필수적이다.
나는 Jekyll 편집기로 RubyMine을 사용하는데 Jekyll이 ruby로 만들어졌기 때문에 편리한 점이 많이 있다.

![No image](/assets/images/posts/20190808/1.png)

오늘 소개해 볼 기능은 Jekyll을 편집할 때 마다 자동으로 브라우저 새로고침이 되도록 도와주는 LiveReload[^livereload] 기능이다. 이 기능을 사용하면 개발 속도가 많이 향상되고, 내가 작성한 게시물의 Markdown 렌더링 결과를 빠르게 미리볼 수 있어서 좋다.
LiveReload 기능은 2018년 1월 2일에 릴리즈 된 Jekyll 3.7.0 부터 적용이 되었다. 

일단 Jekyll 서버를 로컬에서 구동하려면 ruby(>=2.2.5)와 bundler gem, jekyll gem을 설치해야 한다. 자세한 과정은 [이 링크](http://jekyllrb-ko.github.io/docs/installation/)에 있다.
다 설치 했다면 RubyMine이나 본인이 사용하는 편집기에서 블로그 프로젝트를 불러온다.

![No image](/assets/images/posts/20190808/2.png)

그리고 터미널에서 본인의 블로그 프로젝트 경로로 이동한 후 `bundle exec jekyll serve --livereload`를 입력한다.

```shell
# 터미널에서 다음을 입력
$ bundle exec jekyll serve --livereload
```

서버가 잘 구동 되었다면 브라우저에서 `http://localhost:4000` 주소로 접속이 가능하다.

![No image](/assets/images/posts/20190808/3.png)

이제 무언가를 편집해 보자. 서버를 구동할 때 `--livereload` 플래그를 활성화 했기 때문에 편집기에서 코드나 게시물을 수정하고 저장을 누르면 웹 브라우저가 자동으로 새로고침이 된다.

아래의 움짤에서 결과를 확인할 수 있다. 더 이상 마우스를 움직여 브라우저의 새로고침 버튼을 누르거나 F5키를 누르지 않아도 된다.
물론 scss, html 파일 등의 수정 결과도 LiveReload 된다.

![No image](/assets/images/posts/20190808/4.gif)

---

[^jekyll]: [http://jekyllrb-ko.github.io/docs/usage/](http://jekyllrb-ko.github.io/docs/usage/)
[^livereload]: [http://livereload.com/](http://livereload.com/)