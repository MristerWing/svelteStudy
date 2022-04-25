# Svelte

### Default

1. 가상 돔이 아닌 DOM을 사용한다.
2. 상단에 `<script>`를 사용하여 js를 선언하여 사용한다.
3. 상태 관리 라이브러리를 이용하지 않고 js자체에서 재사용한다.
4. `svelte`의 확장자는 `.svelte`이다.

```sevelte
    <script>
        let src = '/img'
    <script>

    <img src={src} alt="img">
```

### CSS

1. css는 `<style>`태그를 이용하여 작성한다.
2. `vue`마냥 templete 패턴으로 작성 된다고 보면 되는 듯?

```
    <p>This is a paragraph.</p>

    <style>sevelte
        /* Write your CSS here */

        p {
            color: puple;
            font-family: 'Comic Sans Ms', cursive;
            font-size: 2em;
        }
    </style>
```

### import component

1. import는 `<script>`태그 내부에서 사용한다.

```svelte
    <script>
        import Nested from './Nested.svelte'
    </script>

    <p>This is a paragraph.</p>
    <Nested />
```

### direct into HTML

1. 변수 사용전`{@html }`를 붙이면 html태그를 직접 삽입할 수 있다.
2. 해당 태그는 `svelte`내에서 퍼포먼스 처리를 하지 않고, XSS공격에 취약하기 때문에 사용시 주의가 필요하다.

```svelte
    <script>
        let string = `this string contains some <strong>HTML!!!</strong>`;
    </script>

    <p>{@html string}</p>
```
