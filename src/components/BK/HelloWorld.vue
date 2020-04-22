<template>
	<v-container>
		<v-row class="text-center">
			<!-- プロフィール -->
			<v-col class="mb-4 grey lighten-5">
				<v-row color="" class="justify-center align-center">
					<h2 class="display-2 font-weight-bold mb-3 justify-center">
					
						<v-icon large="true">mdi-account</v-icon>
						
							<span>Profile</span>
					</h2>
				</v-row>
				<v-avatar size="150" color="grey lighten-4">
					<img
						src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/cf/Angular_full_color_logo.svg/1200px-Angular_full_color_logo.svg.png"
						alt="avatar"
					>
				</v-avatar>
				<p class="headline font-weight">
					和田 修平
				</p>
				<p>
					
				</p>
			</v-col>
		</v-row>
		
		<v-row>
			<v-col md=6>
				<v-card>
					<div class="text-center font-weight-black pt-3">
						サーバーサイドスキル
					</div>
					<v-card-text>
						<v-simple-table>
							<thead>
								<tr>
									<th>言語</th>
									<th>経験</th>
									<th>スキル</th>
								</tr>
							</thead>
							<tbody>
								<tr v-for="item in items" :key="item.lung">
									<td>{{ item.lung }}</td>
									<td>{{ item.year | getDiffYear }}年</td>
									<td><v-rating readonly v-model="item.skill"></v-rating></td>
								</tr>
							</tbody>
						</v-simple-table>
					</v-card-text>
				</v-card>
			</v-col>
		</v-row>
			
		<v-row>
			<v-col
				class="mb-5"
				cols="12"
			>
				<h2 class="headline font-weight-bold mb-3">
					What's next?
				</h2>

				<v-row justify="center">
					<a
						v-for="(next, i) in whatsNext"
						:key="i"
						:href="next.href"
						class="subheading mx-3"
						target="_blank"
					>
						{{ next.text }}
					</a>
				</v-row>
			</v-col>
			
			<v-card>
				<v-card-title>
				</v-card-title>
			
			</v-card>
			
		</v-row>
	</v-container>
</template>

<script>
	export function getThisYear() {
		return new Date().getFullYear();
	}
	
	export default {
		name: 'HelloWorld',
		filters: {
			getDiffYear: function(val) {
				return getThisYear() - val;
			}
		},
		data: () => ({
			backSkills:  [
				{lung: 'Java', year: '2016', skill: 5},
				{lung: 'Python', year: '2016', skill: 3},
				{lung: 'Ruby', year: '2019', skill: 1},
				{lung: 'PHP', year: '2017', skill: 3}
			], 
			frontSkills: [
				{lung: 'HTML', year: '2016', skill: 4},
				{lung: 'CSS', year: '2016', skill: 2},
				{lung: 'JavaScript', year: '2019', skill: 3},
				{lung: 'Sass', year: '2019', skill: 2}
			],
			ecosystem: [
				{
					text: 'vuetify-loader',
					href: 'https://github.com/vuetifyjs/vuetify-loader',
				},
				{
					text: 'github',
					href: 'https://github.com/vuetifyjs/vuetify',
				},
				{
					text: 'awesome-vuetify',
					href: 'https://github.com/vuetifyjs/awesome-vuetify',
				},
			],
			importantLinks: [
				{
					text: 'Documentation',
					href: 'https://vuetifyjs.com',
				},
				{
					text: 'Chat',
					href: 'https://community.vuetifyjs.com',
				},
				{
					text: 'Made with Vuetify',
					href: 'https://madewithvuejs.com/vuetify',
				},
				{
					text: 'Twitter',
					href: 'https://twitter.com/vuetifyjs',
				},
				{
					text: 'Articles',
					href: 'https://medium.com/vuetify',
				},
			],
			whatsNext: [
				{
					text: 'Explore components',
					href: 'https://vuetifyjs.com/components/api-explorer',
				},
				{
					text: 'Select a layout',
					href: 'https://vuetifyjs.com/layout/pre-defined',
				},
				{
					text: 'Frequently Asked Questions',
					href: 'https://vuetifyjs.com/getting-started/frequently-asked-questions',
				},
			],
		}),
	}
</script>
