<template>
	<v-card>
		<div class="text-center font-weight-black pt-3">{{title}}</div>
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
					<tr v-for="item in skills" :key="item.lung">
						<td>{{ item.lung }}</td>
						<td>{{ item.year | getDiffYear }}年</td>
						<td><v-rating readonly v-model="item.skill"></v-rating></td>
					</tr>
				</tbody>
			</v-simple-table>
		</v-card-text>
	</v-card>
</template>

<script>
	export function getThisYear() {
		return new Date().getFullYear();
	}
	
	export default {
		name: 'SkillCard',
		filters: {
			getDiffYear: function(val) {
				return getThisYear() - val;
			}
		},
		
		props: {
			skills:{Object}
			, title:{String}
		}
	}
</script>
