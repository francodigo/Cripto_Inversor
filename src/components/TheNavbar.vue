<template>
	<nav
		class="flex items-center justify-between flex-wrap bg-yellow p-3 fixed w-full shadow"
	>
		<!-- Logo -->
		<a @click="hideMenu()">
			<router-link
				to="/"
				class="flex items-center flex-shrink-0 text-grey_500 mr-24 "
			>
				<Icon class="mr-2" />
				<span class="font-medium text-xl tracking-tighter"
					>Crypto  Inversor</span
				>
			</router-link>
		</a>

		<!-- Button Responsive -->
		<div class="block lg:hidden">
			<button
				@click="toggleMenu()"
				type="button"
				class="flex items-center text-grey_500 border-0 border-none"
			>
				<svg
					class="fill-current h-6 w-6"
					viewBox="0 0 24 24"
					xmlns="http://www.w3.org/2000/svg"
				>
					<title>Menu</title>
					<path
						v-if="!menuShow"
						fill-rule="evenodd"
						d="M3.314,4.8h13.372c0.41,0,0.743-0.333,0.743-0.743c0-0.41-0.333-0.743-0.743-0.743H3.314
						c-0.41,0-0.743,0.333-0.743,0.743C2.571,4.467,2.904,4.8,3.314,4.8z
						M16.686,15.2H3.314c-0.41,0-0.743,0.333-0.743,0.743
						s0.333,0.743,0.743,0.743h13.372c0.41,0,0.743-0.333,0.743-0.743S17.096,15.2,16.686,15.2z
						M16.686,9.257H3.314
						c-0.41,0-0.743,0.333-0.743,0.743s0.333,0.743,0.743,0.743h13.372c0.41,0,0.743-0.333,0.743-0.743S17.096,9.257,16.686,9.257z"
					/>
					<path
						v-if="menuShow"
						fill-rule="evenodd"
						d="M11.469,10l7.08-7.08c0.406-0.406,0.406-1.064,0-1.469c-0.406-0.406-1.063-0.406-1.469,0L10,8.53l-7.081-7.08
							c-0.406-0.406-1.064-0.406-1.469,0c-0.406,0.406-0.406,1.063,0,1.469L8.531,10L1.45,17.081c-0.406,0.406-0.406,1.064,0,1.469
							c0.203,0.203,0.469,0.304,0.735,0.304c0.266,0,0.531-0.101,0.735-0.304L10,11.469l7.08,7.081c0.203,0.203,0.469,0.304,0.735,0.304
							c0.267,0,0.532-0.101,0.735-0.304c0.406-0.406,0.406-1.064,0-1.469L11.469,10z"
					/>
				</svg>
			</button>
		</div>

		<!-- Menu Options Navigation -->
		<div
			class="w-full block flex-grow lg:flex lg:items-center lg:w-auto "
			:class="menuShow ? 'block h-screen' : 'hidden'"
		>
			<div class="text-sm lg:flex-grow">
				<a
					@click="hideMenu()"
					class="block mt-4 lg:inline-block lg:mt-0 text-grey_500 mr-4"
				>
					<router-link to="/dolar">
						Dólar
					</router-link>
				</a>
			</div>
		</div>
	</nav>
</template>

<script>
import Icon from '@/components/Icon';
export default {
	name: 'TheNavbar',
	components: { Icon },
	data() {
		return {
			menuShow: false,
		};
	},
	methods: {
		toggleMenu() {
			this.menuShow = !this.menuShow;
		},
		hideMenu() {
			if (this.menuShow == true) {
				this.menuShow = false;
			}
		},
	},
};
</script>

<style scoped></style>
