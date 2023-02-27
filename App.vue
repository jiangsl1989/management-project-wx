<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style lang="scss">
	@import "./uni_modules/vk-uview-ui/index.scss";
	
	.contains {
		padding: 10px;
	}
	
	.setCenter{
		display: flex;
		flex-direction: column;
		align-items: center;	//水平居中
		justify-content: center;	//垂直居中
	}
</style>
