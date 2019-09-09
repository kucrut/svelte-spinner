<style>
.wrapper {
	max-width: 35em;
	margin-left: auto;
	margin-right: auto;
	text-align: center;
}
nav {
	margin-top: 1em;
	margin-bottom: 1em;
}
:global(a) {
	margin-left: .5em;
	margin-right: .5em;
}
</style>

<script>
	import { Link, Router, Route } from 'svelte-routing';
	import { Feed, Index, Login } from './pages';

	export let url = '';
</script>

<Router url={ url }>
	<div class="wrapper">
		<nav>
			<Link to="/">Home</Link>
			<Link to="/login">Login</Link>
			<Link to="/feed/1">Feed #1</Link>
			<Link to="/feed/2">Feed #2</Link>
		</nav>
		<div>
			<Route path="/feed/:id" component={ Feed } />
			<Route path="/login" component={ Login } />
			<Route component={ Index } />
		</div>
	</div>
</Router>

