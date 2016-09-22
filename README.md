# vue2-ajax-form

```
npm install vue2-ajax-form --save
```

```
<template>
    <ajax-form :action="action" :method="method" :enctype="enctype" :responsetype="responsetype" :before="before" :error="error" :complete="complete" :progress="progress" :after="after">
        <input name="username" type="text" />
        <input value="submit" type="submit" />
    </ajax-form>
</template>
<script>
import ajaxForm from 'vue2-ajax-form'
export default {
    data() {
        action: '/api', // ajax 请求地址 (必须)
        method: 'POST', // ajax 请求方法 POST | GET (默认: POST)
        enctype: 'multipart/form-data', // ajax 请求编码 application/x-www-form-urlencoded | multipart/form-data | text/plain (默认: multipart/form-data)
        responsetype: 'json' // ajax 请求数据类型 blob | document | json | text (默认: json)
    },
    components: {
        ajaxForm
    },
    methods: {
        before() {
            console.log('before')
            // ajax请求前
        },
        error(err) {
            console.log(err)
            // ajax请求出现错误
        },
        complete(response) {
            console.log(response)
            // ajax请求完成
        },
        progress(percent) {
            console.log(percent)
            // ajax请求进度
        },
        after() {
            console.log('after')
            // ajax请求后, 请求未完成
        },
    }
}
</script>
```
