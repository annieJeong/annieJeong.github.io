---
layout: post
title:  "개인 github io 시작하기"
date:   2022-07-15
categories: github
---

github io jekyll [템플릿][jekyll-git]을 사용하여 생성하였다.

repository 생성시 이름을 xxx.github.io 로 생성한다.
>github 가입한 계정과 github.io repository를 동일하게 생성하면 url이 단순하다.   
>동일할 경우 : http://${name}.github.io   
>다를 경우 : http://${name}.github.io/${repository.name}

github repository 생성하여 추가하는 방식도 있지만, [템플릿 페이지][jekyll-git] repository를 fork하여 구축해보았다.   
fork 받은 repository에서 setting > pages 에서 페이지가 세팅되었는지를 확인한다.   

[공식 안내페이지][git-pages] 참고해서 생성.   
fork 해서 받은경우 [템플릿 페이지][jekyll-git]에 작성된 README.md 파일을 참고하여 세팅해준다. 

ruby 개발 환경이 필요하여 ruby 설치 필수.   
devkit이 포함된 버전으로 다운로드 받아 설치한다. [ruby 설치 페이지][ruby-set]   
기본적으로 jekyll 작업환경을 위한 세팅을 해준다. 

```sh
C:\Users\jeong>gem install jekyll
C:\Users\jeong>gem install minima
C:\Users\jeong>gem install bundler
C:\Users\jeong>gem install jekyll-feed
C:\Users\jeong>gem install tzinfo-data
C:\Users\jeong>gem install jekyll-paginate
C:\Users\jeong>gem install liquid
```
[참고][jekyll-set]

만들어둔 repository를 clone 하여 local에 받아둔다.
```sh
jeong@DESKTOP-63NV29O MINGW64 /c/Workspace
$ git clone git@github.com:annieJeong/annieJeong.github.io.git
```

템플릿 README.md 파일 상에 작성된 순서대로 실행해본다.

1. `bundle install`
2. `bundle exec jekyll serve`

2 단계에서 아래와 같은 에러가 발생했다.
```sh
C:\Workspace\annieJeong.github.io>bundle exec jekyll serve
Configuration file: C:/Workspace/annieJeong.github.io/_config.yml
 Theme Config file: C:/Workspace/annieJeong.github.io/_config.yml
            Source: C:/Workspace/annieJeong.github.io
       Destination: C:/Workspace/annieJeong.github.io/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 0.174 seconds.
  Please add the following to your Gemfile to avoid polling for changes:
    gem 'wdm', '>= 0.1.0' if Gem.win_platform?
 Auto-regeneration: enabled for 'C:/Workspace/annieJeong.github.io'
                    ------------------------------------------------
      Jekyll 4.2.2   Please append `--trace` to the `serve` command
                     for any additional information or backtrace.
                    ------------------------------------------------
C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/lib/jekyll/commands/serve/servlet.rb:3:in `require': cannot load such file -- webrick (LoadError)
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/lib/jekyll/commands/serve/servlet.rb:3:in `<top (required)>'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/lib/jekyll/commands/serve.rb:179:in `require_relative'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/lib/jekyll/commands/serve.rb:179:in `setup'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/lib/jekyll/commands/serve.rb:100:in `process'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/lib/jekyll/command.rb:91:in `block in process_with_graceful_fail'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/lib/jekyll/command.rb:91:in `each'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/lib/jekyll/command.rb:91:in `process_with_graceful_fail'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/lib/jekyll/commands/serve.rb:86:in `block (2 levels) in init_with_program'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/mercenary-0.4.0/lib/mercenary/command.rb:221:in `block in execute'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/mercenary-0.4.0/lib/mercenary/command.rb:221:in `each'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/mercenary-0.4.0/lib/mercenary/command.rb:221:in `execute'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/mercenary-0.4.0/lib/mercenary/program.rb:44:in `go'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/mercenary-0.4.0/lib/mercenary.rb:21:in `program'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/exe/jekyll:15:in `<top (required)>'
        from C:/Ruby31-x64/bin/jekyll:32:in `load'
        from C:/Ruby31-x64/bin/jekyll:32:in `<main>'
```
<br/>
명령어에 옵션을 추가하여 실행하라는 에러 발생하여 추가해서 실행하였다.

`bundle exec jekyll serve --trace`

그래도 여전히 에러 발생하고 있었는데

```sh
C:\Workspace\annieJeong.github.io>bundle exec jekyll serve --trace
Configuration file: C:/Workspace/annieJeong.github.io/_config.yml
 Theme Config file: C:/Workspace/annieJeong.github.io/_config.yml
            Source: C:/Workspace/annieJeong.github.io
       Destination: C:/Workspace/annieJeong.github.io/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 0.179 seconds.
  Please add the following to your Gemfile to avoid polling for changes:
    gem 'wdm', '>= 0.1.0' if Gem.win_platform?
 Auto-regeneration: enabled for 'C:/Workspace/annieJeong.github.io'
C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/lib/jekyll/commands/serve/servlet.rb:3:in `require': cannot load such file -- webrick (LoadError)
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/lib/jekyll/commands/serve/servlet.rb:3:in `<top (required)>'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/lib/jekyll/commands/serve.rb:179:in `require_relative'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/lib/jekyll/commands/serve.rb:179:in `setup'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/lib/jekyll/commands/serve.rb:100:in `process'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/lib/jekyll/command.rb:91:in `block in process_with_graceful_fail'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/lib/jekyll/command.rb:91:in `each'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/lib/jekyll/command.rb:91:in `process_with_graceful_fail'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/lib/jekyll/commands/serve.rb:86:in `block (2 levels) in init_with_program'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/mercenary-0.4.0/lib/mercenary/command.rb:221:in `block in execute'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/mercenary-0.4.0/lib/mercenary/command.rb:221:in `each'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/mercenary-0.4.0/lib/mercenary/command.rb:221:in `execute'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/mercenary-0.4.0/lib/mercenary/program.rb:44:in `go'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/mercenary-0.4.0/lib/mercenary.rb:21:in `program'
        from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/exe/jekyll:15:in `<top (required)>'
        from C:/Ruby31-x64/bin/jekyll:32:in `load'
        from C:/Ruby31-x64/bin/jekyll:32:in `<main>'
```

trace 옵션 추가 에러는 사라지고 
```sh
in `require': cannot load such file -- webrick (LoadError)
```

webrick 을 찾을 수 없다는 에러가 발생하고 있었다.

```sh
C:\Workspace\annieJeong.github.io>bundle add webrick
```
webrick 을 추가 후 실행했더니 정상 동작했다.

```sh
C:\Workspace\annieJeong.github.io>bundle exec jekyll serve --trace
Configuration file: C:/Workspace/annieJeong.github.io/_config.yml
 Theme Config file: C:/Workspace/annieJeong.github.io/_config.yml
            Source: C:/Workspace/annieJeong.github.io
       Destination: C:/Workspace/annieJeong.github.io/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 0.174 seconds.
  Please add the following to your Gemfile to avoid polling for changes:
    gem 'wdm', '>= 0.1.0' if Gem.win_platform?
 Auto-regeneration: enabled for 'C:/Workspace/annieJeong.github.io'
    Server address: http://127.0.0.1:4000
  Server running... press ctrl-c to stop.
```

소스 수정후 로컬 서버에서 수정내용을 확인할 수 있고,
push 하면 web페이지에도 반영이되는것을 볼 수 있다.


[git-pages]: https://pages.github.com/
[jekyll-git]: https://github.com/samarsault/plainwhite-jekyll
[ruby-set]: https://rubyinstaller.org/downloads
[jekyll-set]: https://learn.cloudcannon.com/jekyll-blogging/#list
