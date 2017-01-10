<style src="./style.css"></style>

<script>
    import Vue from 'vue'
    import plugin from './plugin'

    let Component = {
        props: {
            visible: {
                type: Boolean,
                required: true
            },
            text: {
                type: String,
                default: '数据加载中'
            }
        },
        render(h) {
            return (
                <transition name="ui-loading-fade">
                    <div class="ui-loading" v-show={this.visible}>
                        <div class="ui-loading__container">
                            <div class="ui-loading__icon"></div>
                            <p class="ui-loading__text">{this.text}</p>
                        </div>
                    </div>
                </transition>
            )
        }
    }

    Vue.use(plugin, Component)

    export default Component
</script>