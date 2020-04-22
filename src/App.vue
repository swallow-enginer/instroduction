<template>
	<v-app>
		<!--ヘッダー-->
		<v-toolbar color="blue" clipped-left fixed app>
			<v-toolbar-title class="headline white--text">
				<span class="font-weight-light">自己紹介</span>
			</v-toolbar-title>
			<v-spacer></v-spacer>
			<v-toolbar-items class="">
			<v-btn class="white--text" depressed="true" color="blue" flat to="/">Home</v-btn>
			<v-btn class="white--text" depressed="true" color="blue" flat to="/about">About</v-btn>
			</v-toolbar-items>
		</v-toolbar>
		
		<v-content>
			<Profile/>
		</v-content>
	</v-app>
</template>

<script>
import Profile from './components/Profile';

export default {
	name: 'App',
	components: {
		Profile,
	},

};
</script>
