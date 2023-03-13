<template>
    <view class="content">
            <div id="dplayer" style="height: 450px; width: 100%;"></div>
        </view>
</template>

<script>
    //引入 hls与dplayer 用于解析播放视频 
    import Hls from 'hls.js'
    import Dplayer from 'dplayer'
    export default {
        data() {
            return {
                dp: {}
            }
        },
        mounted() {
            this.dp = new Dplayer({
                //播放器的一些参数
                container: document.getElementById('dplayer'),
                autoplay: false, //是否自动播放
                theme: '#FADFA3', //主题色
                loop: true,//视频是否循环播放
                lang: 'zh-cn',
                screenshot: false,//是否开启截图
                hotkey: true,//是否开启热键
                preload: 'auto',//视频是否预加载
                volume: 0.7,//默认音量
                mutex: true,//阻止多个播放器同时播放，当前播放器播放时暂停其他播放器
                video: {
                    url: 'https://cd-live-stream.news.cctvplus.com/live/smil:CHANNEL1.smil/playlist.m3u8', //视频地址
                    // url: 'http://boliu.hbzcyc.com/474975DDEFA/474975DDEFA.m3u8', //视频地址
                    type: 'customHls',
                    customType: {
                        customHls: function(video, player) {
                            const hls = new Hls()  //实例化Hls  用于解析m3u8
                            hls.loadSource(video.src)
                            hls.attachMedia(video)
                        }
                    },
                },
            });
        },
        created() {
 
        },
        methods: {
 
        }
    }
</script>


<style>

</style>