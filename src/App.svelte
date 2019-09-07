<script>
    import { Router, Link, Route } from 'svelte-routing';
    import Patients from './pages/patients/Patients.svelte';

    let url = '';
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<Router url="{url}">
    <Route path="patients" component="{Patients}" />
</Router>
