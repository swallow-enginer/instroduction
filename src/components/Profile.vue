<template>
	<v-container>
		<v-row class="text-center">
			<v-col class="mb-4 grey lighten-5">
				<v-row color="" class="justify-center align-center">
					<h2 class="display-1 font-weight-bold mb-3 justify-center">
						<v-icon large="true">mdi-account</v-icon>
						<span>プロフィール</span>
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
		<h2 class="display-1 font-weight-bold mb-3 text-center">
			<v-icon large="true">mdi-xml</v-icon>
			<span>スキル</span>
		</h2>
		<v-row>
			<v-col md=6>
				<SkillCard 
					title="サーバーサイドスキル" 
					:skills="backSkills">
				</SkillCard>
			</v-col>
			<v-col md=6>
				<SkillCard 
					title="フロントエンドスキル" 
					:skills="frontSkills">
				</SkillCard>
			</v-col>
		</v-row>
		<v-row>
			<v-col md=6>
				<SkillCard 
					title="フレームワーク" 
					:skills="frameSkills">
				</SkillCard>
			</v-col>
			<v-col md=6>
				<SkillCard 
					title="DB" 
					:skills="dbSkills">
				</SkillCard>
			</v-col>
		</v-row>
	</v-container>
</template>

<script>
	import SkillCard from '@/components/SkillCard.vue'
	export function getThisYear() {
		return new Date().getFullYear();
	}
	
	export default {
		name: 'Profile',
		filters: {
			getDiffYear: function(val) {
				return getThisYear() - val;
			}
		},
		components: {SkillCard},
		data: () => ({
			backSkills:  [
				{lung: 'Java', year: '2016', skill: 5},
				{lung: 'Python', year: '2016', skill: 3},
				{lung: 'Ruby', year: '2019', skill: 2},
				{lung: 'PHP', year: '2017', skill: 3}
			], 
			frontSkills: [
				{lung: 'HTML', year: '2016', skill: 4},
				{lung: 'CSS', year: '2016', skill: 2},
				{lung: 'JavaScript', year: '2019', skill: 3},
				{lung: 'Sass', year: '2019', skill: 2}
			],
			frameSkills: [
				{lung: 'Ruby on Rails', year: '2019', skill: 2},
				{lung: 'WordPress', year: '2017', skill: 3},
				{lung: 'BootStrap', year: '2018', skill: 3},
				{lung: 'Vue', year: '2019', skill: 2}
			],
			dbSkills: [
				{lung: 'PostgreSQL', year: '2017', skill: 5},
				{lung: 'MySql', year: '2017', skill: 3},
				{lung: 'Oracle', year: '2016', skill: 3},
			]
		}),
	}
</script>
