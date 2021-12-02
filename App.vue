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

<style>
	/*每个页面公共css */
	@font-face {
		font-family: 'iconfont';
		src: url('./static/font_nav/iconfont.eot');
		src: url('./static/font_nav/iconfont.eot?#iefix') format('embedded-opentype'),
			url('./static/font_nav/iconfont.woff2') format('woff2'),
			url('./static/font_nav/iconfont.woff') format('woff'),
			url('./static/font_nav/iconfont.ttf') format('truetype'),
			url('./static/font_nav/iconfont.svg#iconfont') format('svg');
	}
</style>
