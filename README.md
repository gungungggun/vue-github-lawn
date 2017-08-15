# vue-github-lawn

A github lawn Vue component, Compatible with Vue 2.x

## Install

``` sh
npm install vue-github-lawn
```

``` js
import GithubLawn from 'vue-github-lawn'

Vue.component('my-component', {
    components: {
        GithubLawn
    }
});
```

## Usage
```
<github-lawn :data="data" :last="last" :unit="'contributions'"></github-lawn>
```

## Avaliable props
| Prop | Type   | Default       | Description                                                   |
| :--- | :---   | :------       | :---------                                                    |
| data | Array  | []            | Input data. The data must be sorted latest. example [2, 5, 8] |
| last | String | null          | Input latest date.                                            |
| unit | String | contributions | Tooltip message.                                              |
| week | Number | 53            | column size.                                                  |
