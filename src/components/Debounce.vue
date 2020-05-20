<template>
    <div>
       <div> 防抖 </div>
        <div>
            <button @click="testClick">测试防抖</button>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Debounce",
        data() {
            return {
                timeOut: null
            }
        },
        mounted() {
        },
        methods: {
            // 比如说我们一直点击按钮  只有不点击按钮之后1秒才会触发

            // 防抖：任务频繁触发的情况下，只有任务触发的间隔超过指定间隔的时候，任务才会执行
            // 通俗来讲：所谓防抖，就是指触发事件后在 n 秒内函数只能执行一次，如果在 n 秒内又触发了事件，则会重新计算函数执行时间。

            testClick() {
                console.log("---点击事件触发---");
                this.debounce(this.sayDebounce)
            },
            debounce(fn) {
                if (this.timeOut) clearTimeout(this.timeOut);
                this.timeOut = setTimeout(() => {
                    fn()
                }, 1000);
            },
            // 防抖之后触发的函数
            sayDebounce() {
                console.log("防抖成功！");
            }
        }
    }
</script>

<style scoped>

</style>
