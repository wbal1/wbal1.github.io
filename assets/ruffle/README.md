# ruffle-selfhosted

ruffle-selfhosted는 Ruffle을 당신의 웹 사이트에 올리기 위한 의도적인 방법입니다.

당신은 이를 포함하고 이에 대해서 잊어버리고, 우리는 존재하는 플래시 컨텐츠를 변환할 것이거나,
또는 사용자 정의 설정 혹은 Ruffle 플레이어의 더욱 진보된 사용을 위해 우리의 API를 사용할 수 있습니다.

## ruffle-selfhosted의 사용

더 많은 예시와 당신의 웹사이트 상에서 어떻게 Ruffle을 사용할 지에 대한 심도있는 문서를 원한다면,
[우리 위키를 방문해 주세요.](https://github.com/ruffle-rs/ruffle/wiki/Using-Ruffle#web)

### Ruffle 호스팅하기

`selfhosted` 패키지는 번들러나 npm을 쓰지 않고 그냥 작동하기만 하는 것을 원하는 웹사이트들 위해
설정되었습니다. 만약 당신이 npm과 번들러를 통해 Ruffle을 쓰고 싶다면,
[ruffle core를 참조해 주세요.](https://github.com/ruffle-rs/ruffle/tree/master/web/packages/core)

Ruffle을 당신 웹사이트에 사용하는 것을 시작하기 전에, 당신은 Ruffle의 파일을 직접 호스팅해야 합니다.
[최신 빌드](https://github.com/ruffle-rs/ruffle/releases)를 가져가거나
[당신이 직접 만들고](https://github.com/ruffle-rs/ruffle/blob/master/web/README.md), 이러한 파일이 당신 웹 서버로부터 하여금 접근 가능하게 만드십시오.

`.wasm` 파일은 올바르게 제공되어야 하며, 일부 웹 서버는 이 파일들을 즉시 실행시키지 못하게 할 수 있습니다.
만일 `Incorrect response MINE type` 오류를 마주친다면 [우리 위키](https://github.com/ruffle-rs/ruffle/wiki/Using-Ruffle#configure-wasm-mime-type)에서
이를 어떻게 설정할 지에 대한 지침을 봐 주십시오.

### "플러그 앤 플레이"

만약 당신이 플래시 컨텐츠가 있는, 이미 있는 웹 사이트가 있다면, 당신은 단순히 Ruffle을 스크립트로써 포함하고
우리의 변환 마술은 당신을 위해 모든 것을 대체할 것입니다. 호들갑을 떨지도, 어지럽히지도 않습니다.

```html
<script src="path/to/ruffle/ruffle.js"></script>
```

### Javascript API

만일 당신이 Ruffle 플레이어를 조작하고 싶으시다면, 당신은 우리의 Javascript API를 사용할 수 있습니다.

```html
<script>
    window.RufflePlayer = window.RufflePlayer || {};

    window.addEventListener("DOMContentLoaded", () => {
        let ruffle = window.RufflePlayer.newest();
        let player = ruffle.createPlayer();
        let container = document.getElementById("container");
        container.appendChild(player);
        player.load("movie.swf");
    });
</script>
<script src="path/to/ruffle/ruffle.js"></script>
```

## 빌드, 테스트 혹은 기여

[ruffle-web README](https://github.com/ruffle-rs/ruffle/blob/master/web/README.md)를 참조해 주십시오.
