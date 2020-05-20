<template>
    <div>
        <div> 节流 </div>
        <div>
            <button @click="testClick">测试节流</button>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Throttle",
        data() {
            return {
                canRun: true
            }
        },
        methods: {
            // 比如说我们一直点击按钮  1秒之后会触发一次  然后1秒之后又会触发一次......

            // 节流：指定时间间隔内只会执行一次任务
            // 通俗来讲：所谓节流，就是指连续触发事件但是在 n 秒中只执行一次函数。 节流会稀释函数的执行频率。

            testClick() {
                console.log("---点击事件触发---");
                this.throttle(this.sayThrottle)
            },
            throttle(fn) {
                if(!this.canRun) return;
                this.canRun = false;
                setTimeout( () => {
                    fn();
                    this.canRun = true;
                }, 1000);
            },
            sayThrottle() {
                console.log("节流成功！")
            }
        }
    }
</script>

<style scoped>

</style>
