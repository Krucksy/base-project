<script>
import { RouterLink, RouterView } from "vue-router"
import VueNav from '@/components/Nav.vue'
import VueFooter from '@/components/Footer.vue'
import LoadingBar from '@/components/Loadingbar.vue'

export default {
    data(){
		return {
			progress: 0,
			status: "doesn't start yet",
			error: false,
			direction: false
		};
	},

    components: {
        RouterLink,
        RouterView,
        VueNav,
        VueFooter,
        LoadingBar
    },

	methods: {
		progressTo(val){
			this.progress = val;
		},
		setToError(bol){
			this.error = bol;
			this.status = "Error";
		},
		changeDirection(direction){
			if(this.progress > 0){
				this.progress = 100;
			}
			this.direction = !this.direction;
		}
	},

	events: {
		/**
		*	Global Loading Callback Event
		*
		*	@event-name loading-bar:{event-name}
		*/
		// Loading Bar on started
		'loading-bar:started': function (){
			console.log('started');
			this.status = "started";
		},

		// Loading Bar on loading
		'loading-bar:loading': function (){
			console.log('loading');
			this.status = "loading";
		},

		// Loading Bar on loaded
		'loading-bar:loaded': function (){
			console.log('loaded');
			this.status = "loaded";
		},

		// Loading Bar on error
		'loading-bar:error': function (){
			console.log('error');
			this.status = "error";
		},
	},

	ready(){
		var self = this;
			self.progress = 10;
			for (var i = 0; i < 30; i++) {
				if(i > 20 && i < 29){
					setTimeout(function () {
						self.progress += 5;
					},50*i);
				}else{
					setTimeout(function () {
						self.progress ++;
					},10*i);
				}
			}
			setTimeout(function () {
				self.progress = 100;
			},1500);
	}
}


</script>

<template>
    <metainfo>
        <template v-slot:title="{ content }">
            {{
                content ? `${content} | TEST` : `TEST`
            }}
        </template>
    </metainfo>
	<LoadingBar :progress.sync="progress" :direction="direction ? 'left' : 'right'" :error.sync="error"></LoadingBar>
    <VueNav></VueNav>
    <div class="container">
        <RouterView />
    </div>
    <VueFooter></VueFooter>
</template>

<style lang=scss>
@import "@/assets/style/normalise.css";
@import "@/assets/style/bases.scss";
</style>
