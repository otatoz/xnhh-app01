<script>
export default {
    data(){
        return {
            msg:'hello render'
        }
    },
    created(){
        // alert('created')
        console.log('created',this.$refs.myRef)
    },
    mounted(){
        // alert('mounted')
        console.log('mounted',this.$refs.myRef)
        // console.log(document.getElementById('xpf'),'---')
    },
    // 渲染函数
    render:function(createElement){
        // alert('render')
        return createElement('h2',{
            ref: 'myRef',
            // 添加类名
            'class':{
                one:true
            },
            // 添加样式
            style:{
                color:'red',
                'background-color':'#ccc',
                fontSize:'40px'
            },
            // 添加普通属性
            attrs:{
                id:'xpf',
                name:'vue'
            },
            // 添加事件
            on:{
                click:this.clickHandler
            }
        },this.msg)
    },
    methods:{
        clickHandler(){
            this.msg = 'hello world,hello vue'
        }
    }
}
</script>