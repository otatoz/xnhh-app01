<script>
export default {
    render:function(createElement){
        return createElement('div',{
            attrs:{
                id:'main'
            },
            style:{
                height:'400px',
                width:'600px'
            }
        })
    },
    data(){
        return {
            articles:{
                x:["衬衫","羊毛衫","雪纺衫","裤子","高跟鞋","袜子"],
                y:[5, 20, 36, 10, 10, 20]
            }
        }
    },
    methods:{
        initEchart(){
            // 基于准备好的dom，初始化echarts实例
            var myChart = echarts.init(document.getElementById('main'));
            // 指定图表的配置项和数据
            var option = {
                title: {
                    text: 'ECharts 入门示例'
                },
                tooltip: {},
                legend: {
                    data:['销量']
                },
                xAxis: {
                    data: this.articles.x
                },
                yAxis: {},
                series: [{
                    name: '销量',
                    type: 'bar',
                    data: this.articles.y
                }]
            };
            // 使用刚指定的配置项和数据显示图表。
            myChart.setOption(option);
        }
    },
    mounted(){
        this.initEchart();
    }
}
</script>